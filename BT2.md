# BT2 – Quản lý việc học của sinh viên trong một học kỳ

## 1. Mô tả bài toán
Một sinh viên muốn quản lý việc học của mình trong một học kỳ bằng máy tính. Sinh viên quan tâm đến:
- Các **môn học** đang học
- **Mục tiêu học tập** cho từng môn

---

## 2. Xác định các thực thể (Entities)

### 2.1. SinhVien
Đại diện cho sinh viên sử dụng hệ thống.

**Thuộc tính:**
- `MaSV` (PK): Mã sinh viên
- `TenSV`: Tên sinh viên

---

### 2.2. MonHoc
Đại diện cho các môn học mà sinh viên đang học.

**Thuộc tính:**
- `MaMon` (PK): Mã môn học
- `TenMon`: Tên môn học
- `SoTinChi`: Số tín chỉ

---

### 2.3. MucTieuHocTap
Đại diện cho mục tiêu học tập của từng môn.

**Thuộc tính:**
- `MaMucTieu` (PK): Mã mục tiêu
- `NoiDung`: Nội dung mục tiêu học tập (ví dụ: đạt điểm cao, nắm vững kiến thức)
- `MaMon` (FK): Mã môn học

---

## 3. Xác định mối quan hệ giữa các thực thể

### 3.1. Quan hệ SinhVien – MonHoc
- **Loại quan hệ:** 1 – N
- **Mô tả:** Một sinh viên có thể học **nhiều môn học**, mỗi môn học thuộc về **một sinh viên**.

---

### 3.2. Quan hệ MonHoc – MucTieuHocTap
- **Loại quan hệ:** 1 – N
- **Mô tả:** Một môn học có thể có **nhiều mục tiêu học tập**, mỗi mục tiêu chỉ thuộc về **một môn học**.

---

## 4. Tóm tắt mô hình ERD (dạng text)

```
SinhVien (MaSV, TenSV)
   1 ─── N
MonHoc (MaMon, TenMon, SoTinChi, MaSV)
   1 ─── N
MucTieuHocTap (MaMucTieu, NoiDung, MaMon)
```

---

## 5. Ghi chú
- Mô hình phù hợp cho bài toán quản lý học tập cá nhân trong một học kỳ
- Có thể mở rộng thêm: điểm số, thời khóa biểu, tiến độ hoàn thành
