# Báo cáo cá nhân — NguyenQuangThuc-2A202603116

Đổi tên file theo quy tắc `MSSV_HoTen.md`. Ví dụ: `20241234_NguyenVanAn.md`.

Dữ liệu: 12 ảnh người COCO val2017 (Lin et al., 2014) và 8 ảnh chân dung Wikimedia Commons, chỉ dùng trong lớp.

## 0. Thông tin học viên

- Họ tên: Nguyen Quang Thuc
- MSSV: 2A202603116
- Email: **Cần bổ sung**
- Link repository: https://github.com/ThucNguyen-97/K5-L2A-Day4-NguyenQuangThuc-2A202603116-KeypointPose-S
- Phiên bản CVAT (Help → About): 2.82.0
- Máy: **Cần bổ sung hệ điều hành / RAM / chế độ CVAT**
- Bộ ảnh (`src/exports/assignment.json` do `lab.py setup` tạo): có
- Giờ bắt đầu:
- Giờ kết thúc:

## 1. Kiểm tra label (CP0)

| Label | Kiểu | Số điểm | Tên điểm đúng bảng của lab? | Đúng thứ tự? | Số cạnh |
|---|---|---:|---|---|---:|
| `person` | Skeleton | 17 | Có | Có | 19 |
| `face` | Skeleton | 13 | Có | Có | 13 |

Mẫu `person` dựng theo người quay mặt về camera (các điểm `left_*` nằm bên phải khung mẫu)? Có / Không

Cách đổi cờ `occluded` / `outside` cho **một điểm** trên phiên bản CVAT này (một câu):

Trên CVAT, chọn điểm cần đổi rồi bật thuộc tính `Occluded` hoặc `Outside` trong phần thuộc tính của điểm; `Outside` dùng cho điểm ngoài khung, `Occluded` dùng khi điểm bị che nhưng vẫn ước lượng được.

## 2. Số lượng đã gán và thời gian (CP1, CP2)

| Nhóm ảnh | Số ảnh | Số skeleton đã gán | Số người dưới 60 px (không gán) | Số poster / gương / màn hình bỏ qua | Thời gian (phút) |
|---|---:|---:|---:|---:|---:|
| `easy` | 5 | 5 | **Cần bổ sung** | 0 | **Cần bổ sung** |
| `occluded` | 3 | 6 | **Cần bổ sung** | 0 | **Cần bổ sung** |
| `back` | 2 | 3 | **Cần bổ sung** | 0 | **Cần bổ sung** |
| `small` | 1 | 3 | **Cần bổ sung** | 0 | **Cần bổ sung** |
| `crowd` | 1 | 1 | **Cần bổ sung** | 0 | **Cần bổ sung** |
| `faces` | 8 | 8 | — | 0 | **Cần bổ sung** |

- Số ảnh người đã xong ở mốc phút 105: ___ / 10
- Thời gian thực tế (phút): CP1 ___ · CP2 ___ · CP3 ___
- Ảnh tốn thời gian nhất là ảnh nào, vì sao?

**Cần bổ sung từ nhật ký làm bài.**

## 3. Bảng ca khó (CP1, CP2)

Mỗi điểm bạn phân vân một dòng, nhất là phân vân giữa `v = 1` và `v = 0`, hoặc không chắc hướng người.

| Ảnh | Người / mặt | Điểm | Cờ đã chọn | Phân vân giữa | Lý do chọn |
|---|---|---|---:|---|---|
| 000000522889.jpg | người | ankle / knee | cảnh báo `lr_swap` | Script phát hiện cặp trái/phải ngược phía; cần review trên ảnh | Cần xác nhận |
| 000000515309.jpg | người | elbow | cảnh báo `lr_swap` | Script phát hiện cặp trái/phải ngược phía; cần review trên ảnh | Cần xác nhận |
| 000000308257.jpg | người | ankle | cảnh báo `lr_swap` | Script phát hiện cặp trái/phải ngược phía; cần review trên ảnh | Cần xác nhận |
| 000000188804.jpg | người | ankle | cảnh báo `lr_swap` | Script phát hiện cặp trái/phải ngược phía; cần review trên ảnh | Cần xác nhận |
| 000000269462.jpg | người | — | ok / cần review | Có nhiều skeleton trong ảnh; kiểm lại không gán thừa | Cần xác nhận |
| face_79367.jpg | mặt | — | ok | Script không báo lỗi | Chưa review tay |
| face_53580.jpg | mặt | — | ok | Script không báo lỗi | Chưa review tay |
| face_442231.jpg | mặt | — | ok | Script không báo lỗi | Chưa review tay |

## 4. Bảng tự review (CP3)

Đi từ ảnh cuối về ảnh đầu. 5 ảnh người (ít nhất 2 ảnh `back` hoặc `crowd`) và 3 ảnh mặt. Ít nhất 8 dòng, kể cả dòng `ok`. Ghi lỗi trước, sửa sau.

Mã lỗi dùng đúng một trong: `lr_swap`, `vis_flag`, `position`, `missing`, `extra`, `ok`.

| Ảnh | Người / mặt | Điểm | Mã lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|---|
| 4 | 0 | 0 | 0 | 0 | 4 |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |

Tổng hợp số lỗi theo mã:

| `lr_swap` | `vis_flag` | `position` | `missing` | `extra` | `ok` |
|---:|---:|---:|---:|---:|---:|
| | | | | | |

Điểm còn phân vân giữa `v = 1` và `v = 0` (ghi cả hai lựa chọn và lý do chọn):

Bốn cảnh báo `lr_swap` ở các ảnh `000000188804.jpg`, `000000308257.jpg`, `000000515309.jpg`, `000000522889.jpg` cần được xem lại trực tiếp trên ảnh để phân biệt lỗi trái/phải với tư thế tay/chân bắt chéo thật.

## 5. Kiểm file xuất và kết quả tự kiểm (CP4)

Tự kiểm tay trong file JSON:

| File | Người / mặt kiểm (ảnh, thứ tự) | Số phần tử `keypoints` | Điểm `outside` ra `v = 0`, `occluded` ra `v = 1`? | `num_keypoints` khớp? |
|---|---|---:|---|---|
| `NguyenQuangThuc_persons.zip` | 000000057978.jpg, skeleton #1 | 51 | Có | Có |
| `NguyenQuangThuc_persons.zip` | 000000188804.jpg, skeleton #1 | 51 | Có | Có |
| `NguyenQuangThuc_faces.zip` | face_155465.jpg, skeleton #1 | 39 | Có | Có |

Sau khi xuất, CVAT ghi `occluded` thành `v = 1` và `outside` thành `v = 0`. Tọa độ của điểm `outside` trong file là tọa độ cũ; script ghi chú đây không phải lỗi vì điểm `v = 0` bị bỏ qua khi huấn luyện và chấm.

Hai job đã chuyển sang completed trên CVAT? Có

Dán phần **TÓM TẮT** in ra từ `src/check_submission.py`:

```text
- File person: `NguyenQuangThuc_persons.zip`
  - Số ảnh: 12 · số skeleton `person`: 18 · mỗi annotation 51 số
  - Cờ v: v=2 219 (72%) · v=1 35 (11%) · v=0 52 (17%)
  - `num_keypoints` trung bình: 14.1
- File face: `NguyenQuangThuc_faces.zip`
  - Số ảnh: 8 · số skeleton `face`: 8 · mỗi annotation 39 số
  - Cờ v: v=2 94 (90%) · v=1 10 (10%) · v=0 0 (0%)
  - `num_keypoints` trung bình: 13.0
- Số lỗi: 0 · số cảnh báo: 4 · Kết quả: ĐẠT
```

Các `[CẢNH BÁO]` còn giữ nguyên và lý do:

**Cần bổ sung nhận xét sau khi review trực tiếp bốn cảnh báo `lr_swap`.**

## 6. Ảnh chụp màn hình

1. Label `person` trong label constructor (đủ 17 điểm có tên):

   ![Label person](images/1_label_person.png)

2. Một người quay lưng đã gán, cờ đã đặt:

   ![Người quay lưng](images/2_nguoi_quay_lung.png)

3. Một khuôn mặt đã gán 13 điểm, phóng to vùng mắt:

   ![Khuôn mặt phóng to](images/3_mat_phong_to.png)

4. Một đoạn JSON xuất của một người:

   ![JSON export](images/4_json_export.png)

Nguồn ảnh: COCO val2017 / Wikimedia Commons.

## 7. Tự đánh giá

1. Lỗi bạn mắc nhiều nhất hôm nay, và cách bạn sẽ tránh ở dự án thật:

   **Cần bổ sung sau khi tự review.**

2. Một quy tắc bạn đề xuất thêm vào guideline (kèm ảnh ví dụ nếu có):

   **Cần bổ sung sau khi tự review.**

3. Nhãn của bạn đi vào model ở đâu? Chọn một lỗi bạn đã sửa và nói nó sẽ làm model học sai thế nào (heatmap, trọng số trong loss, hay bước lật ảnh):

   **Cần bổ sung sau khi tự review.**

## 8. Khó khăn và lỗi kỹ thuật

**Cần bổ sung các lỗi kỹ thuật / thời gian thực tế nếu có.**

## Bonus (nếu làm)

### B1 — 3 ảnh người khó thêm

| Ảnh | Số skeleton | Số người dưới 60 px | Ca khó nhất |
|---|---:|---:|---|
| | | | |
| | | | |
| | | | |

Kết quả `src/check_submission.py` cho `HoVaTen_bonus_persons.zip`:

```text
(dán ở đây)
```

### B2 — 5 ảnh khuôn mặt đen trắng / hồng ngoại

Ảnh không màu khó hơn ở điểm nào? Kính râm trên ảnh hồng ngoại có còn là `v = 1` không?

...

### B3 — Model so với nhãn của tôi (không tính điểm)

- Demo đã dùng:
- Ảnh đã thử:

1. Model có trả điểm cho khớp bị che, hay khớp ngoài ảnh không? Confidence ở các điểm đó thế nào?

   ...

2. Với người quay lưng, model có đổi trái/phải không?

   ...

3. Bộ điểm của model có giống 17 điểm COCO không?

   ...

## 9. Tài liệu tham khảo và công cụ AI đã dùng

...
