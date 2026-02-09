# Hướng dẫn: Develop Serverless Applications on Cloud Run (Challenge Lab GSP328)

Đây là bài lab dạng "Challenge" (Thử thách), nghĩa là Google chỉ đưa ra yêu cầu chứ không hướng dẫn chi tiết từng nút bấm. Dưới đây là lời giải (Solution) để bạn hoàn thành các nhiệm vụ thông qua **Google Cloud Shell**.

> **💡 Mẹo:** Nên dùng Cloud Shell thay vì giao diện Web để thao tác nhanh và chính xác hơn.

---

## 🛠️ Chuẩn bị (Setup)

1.  Mở **Cloud Shell** (biểu tượng `>_` trên thanh menu xanh).
2.  Thiết lập các biến môi trường để dùng cho tiện (đỡ phải gõ lại nhiều lần):
    ```bash
    # Thay thế [PROJECT_ID] bằng ID dự án thực tế của bạn (xem ở góc trái màn hình lab)
    export PROJECT_ID=[PROJECT_ID]
    export REGION=us-central1
    gcloud config set project $PROJECT_ID
    gcloud config set run/region $REGION
    gcloud config set run/platform managed
    ```
3.  Clone mã nguồn của bài Lab:
    ```bash
    git clone https://github.com/googlecodelabs/monolith-to-microservices.git
    cd monolith-to-microservices
    ```

---

## 🚀 Nhiệm vụ 1: Kích hoạt dịch vụ Billing công khai (Enable public service)

*Yêu cầu: Build image `billing-staging-api:0.1`, deploy unauthenticated.*

```bash
# Di chuyển vào thư mục code
cd ~/monolith-to-microservices/pet-theory/lab07/unit-api-billing

# Build Docker Image
gcloud builds submit --tag gcr.io/$PROJECT_ID/billing-staging-api:0.1 .

# Deploy lên Cloud Run
gcloud run deploy billing-staging-api \
  --image gcr.io/$PROJECT_ID/billing-staging-api:0.1 \
  --allow-unauthenticated \
  --region $REGION
```
*Sau khi chạy xong, copy URL của service này lại để test.*

---

## 🚀 Nhiệm vụ 2: Triển khai dịch vụ Frontend (Deploy frontend service)

*Yêu cầu: Build image `frontend-staging:0.1`, deploy unauthenticated.*

```bash
# Di chuyển vào thư mục code
cd ~/monolith-to-microservices/pet-theory/lab07/staging-frontend-billing

# Build Docker Image
gcloud builds submit --tag gcr.io/$PROJECT_ID/frontend-staging:0.1 .

# Deploy lên Cloud Run
gcloud run deploy frontend-staging \
  --image gcr.io/$PROJECT_ID/frontend-staging:0.1 \
  --allow-unauthenticated \
  --region $REGION
```

---

## 🚀 Nhiệm vụ 3: Triển khai dịch vụ riêng tư (Deploy private service)

*Yêu cầu: Build image `billing-staging-api:0.2`, deploy AUTHENTICATED (riêng tư).*

```bash
# Di chuyển vào thư mục code
cd ~/monolith-to-microservices/pet-theory/lab07/staging-api-billing

# Build Docker Image mới
gcloud builds submit --tag gcr.io/$PROJECT_ID/billing-staging-api:0.2 .

# Xóa service cũ (nếu cần, nhưng thường deploy đè cũng được) và Deploy service mới yêu cầu xác thực
gcloud run deploy billing-staging-api \
  --image gcr.io/$PROJECT_ID/billing-staging-api:0.2 \
  --no-allow-unauthenticated \
  --region $REGION

# Lấy URL của Billing Service vừa deploy
BILLING_URL=$(gcloud run services describe billing-staging-api --format 'value(status.url)')
echo $BILLING_URL
```

---

## 🚀 Nhiệm vụ 4: Tạo Service Account cho Billing

*Yêu cầu: Tạo SA `billing-service`.*

```bash
gcloud iam service-accounts create billing-service \
  --display-name "Billing Service Cloud Run"
```

---

## 🚀 Nhiệm vụ 5: Triển khai Billing Service với Service Account

*Yêu cầu: Build `billing-prod-api:0.1`, deploy authenticated, gắn SA `billing-service`.*

```bash
# Di chuyển vào thư mục code
cd ~/monolith-to-microservices/pet-theory/lab07/prod-api-billing

# Build Image
gcloud builds submit --tag gcr.io/$PROJECT_ID/billing-prod-api:0.1 .

# Deploy với Service Account
gcloud run deploy billing-prod-api \
  --image gcr.io/$PROJECT_ID/billing-prod-api:0.1 \
  --no-allow-unauthenticated \
  --service-account billing-service@$PROJECT_ID.iam.gserviceaccount.com \
  --region $REGION

# Lấy URL của Prod Billing Service
PROD_BILLING_URL=$(gcloud run services describe billing-prod-api --format 'value(status.url)')
echo $PROD_BILLING_URL
```

---

## 🚀 Nhiệm vụ 6: Tạo Service Account cho Frontend

*Yêu cầu: Tạo SA `frontend-prod-service`, cấp quyền `run.invoker` để nó gọi được Billing.*

```bash
# 1. Tạo Service Account
gcloud iam service-accounts create frontend-prod-service \
  --display-name "Billing Service Cloud Run Invoker"

# 2. Cấp quyền cho SA này được phép gọi (invoke) Billing Service
gcloud run services add-iam-policy-binding billing-prod-api \
  --member=serviceAccount:frontend-prod-service@$PROJECT_ID.iam.gserviceaccount.com \
  --role=roles/run.invoker \
  --region $REGION
```

---

## 🚀 Nhiệm vụ 7: Triển khai lại Frontend với Service Account

*Yêu cầu: Build `frontend-prod:0.1`, deploy unauthenticated, gắn SA `frontend-prod-service`, set biến môi trường URL.*

```bash
# Di chuyển vào thư mục code
cd ~/monolith-to-microservices/pet-theory/lab07/prod-frontend-billing

# Build Image
gcloud builds submit --tag gcr.io/$PROJECT_ID/frontend-prod:0.1 .

# Deploy Frontend
gcloud run deploy frontend-prod-service \
  --image gcr.io/$PROJECT_ID/frontend-prod:0.1 \
  --allow-unauthenticated \
  --service-account frontend-prod-service@$PROJECT_ID.iam.gserviceaccount.com \
  --set-env-vars BILLING_SERVICE_URL=$PROD_BILLING_URL \
  --region $REGION
```

---

## ✅ Kiểm tra và Hoàn thành
1.  Sau khi chạy xong mỗi cụm lệnh, hãy quay lại trang lab và bấm **Check my progress**.
2.  Nếu báo lỗi đỏ, hãy kiểm tra kỹ xem Service Name hoặc Image Tag có sai chính tả không.
3.  Khi đủ 100 điểm -> **End Lab**.

Chúc bạn thành công!
