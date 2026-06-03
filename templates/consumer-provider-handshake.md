# Consumer–Provider Handshake

## Thông tin chung

- Lab: FIT4110 Lab 03
- Ngày: 03/06/2026
- Provider team: Nhóm phụ trách User Service
- Consumer team: Nhóm 3 (Nguyễn Xuân Anh, Vũ Đức Nguyễn Chuẩn, Tăng Tất Cương)
- Provider service: User Service
- Consumer service: Notification Service (Dịch vụ gửi cảnh báo đa kênh)

## Contract

- Contract file: `contracts/core-notification.openapi.yaml`
- Mock base URL: `http://localhost:4012`
- Auth method: Bearer Token (JWT)
- Endpoint được test: `GET /internal/users/{userId}/contact`

## Smoke test

### Request

```http
GET /internal/users/SV-2026-001/contact
Authorization: Bearer {{authToken}}
Content-Type: application/json
```

```json
{}
```

### Expected response

```json
{
  "userId": "SV-2026-001",
  "email": "sv001@example.edu.vn",
  "phone": "0901234567",
  "deviceToken": null
}
```

## Kết quả

- [x] Consumer gọi mock thành công.
- [x] Consumer parse được field cần dùng.
- [x] Consumer hiểu lỗi 4xx/5xx provider trả về.
- [x] Có Newman report hoặc screenshot.

## Ghi chú thay đổi hợp đồng

| Nội dung | Trước | Sau | Người đồng ý |
|---|---|---|---|
| Xử lý khi User Service trả về 404 | Chờ timeout | Trả về trạng thái FAILED cho thông báo báo | Nhóm 3 |

## Xác nhận

- Provider representative: Đại diện nhóm User Service
- Consumer representative: Đại diện Nhóm 3 (Notification Service)
