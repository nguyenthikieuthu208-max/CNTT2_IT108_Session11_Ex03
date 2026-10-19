


# Bài 3: Chuẩn hóa quy trình tra cứu dữ liệu kho hàng

## Phần 1: Phân tích VLOOKUP

Tham số

Ý nghĩa

`Lookup_value`

Mã linh kiện trong sheet `Don_Hang`, ví dụ A2

`Table_array`

Bảng tra cứu trong sheet `Danh_Muc`, ví dụ `$A$2:$C$101`

`Col_index_num`

`2` lấy Tên linh kiện, `3` lấy Đơn giá

`Range_lookup`

`FALSE` để tìm chính xác mã linh kiện

## Phần 2: Công thức triển khai

1. Lấy Tên linh kiện (ô B2):

```
=IFERROR(VLOOKUP(TRIM(A2),Danh_Muc!$A$2:$C$101,2,FALSE),"Không tìm thấy")
```

2. Lấy Đơn giá (ô C2):

```
=IFERROR(VLOOKUP(TRIM(A2),Danh_Muc!$A$2:$C$101,3,FALSE),"Không tìm thấy")
```

Giải thích:

-   `TRIM`: Loại bỏ khoảng trắng thừa ở đầu và cuối mã tra cứu.
    
-   `$`: Cố định vùng dữ liệu khi kéo công thức xuống.
    
-   `FALSE`: Tìm kiếm chính xác.
    
-   `IFERROR`: Hiển thị thông báo dễ hiểu nếu xảy ra lỗi.
