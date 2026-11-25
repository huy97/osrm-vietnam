# osrm-vietnam

Build dữ liệu OSRM (MLD, xe ô tô) cho bản đồ Việt Nam từ Geofabrik và đẩy lên máy chủ chạy `osrm-routed` (osrm.iot4vn.com).

- Chạy tay ở tab Actions (workflow `build`), hoặc tự chạy ngày 1 hằng tháng.
- Máy chủ chỉ nhận đúng 2 lệnh từ khoá CI (`/srv/osrm/ci-gate.sh`): rsync vào `/srv/osrm/incoming/<tên>/` và `activate <tên>`.
- `activate` chuyển bản mới vào `/srv/osrm/releases/<tên>`, chạy lại container `osrm`, thử một tuyến; lỗi thì quay về bản trước.
- Bản cũ trong `/srv/osrm/releases` không tự xoá, dọn bằng tay.
- Secrets: `OSRM_SSH_KEY`, `OSRM_KNOWN_HOSTS`, `OSRM_HOST`, `OSRM_PORT`.
