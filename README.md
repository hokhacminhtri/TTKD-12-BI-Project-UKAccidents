<h1 align="center">
  Đồ án thực hành - Môn học Hệ thống thông tin phục vụ trí tuệ kinh doanh
</h1>

<h2 align="center">
  BI Project - UK Accidents
</h2>

---

## Nhóm TTKD-12

- 1712766 - Nguyễn Chí Thanh
- 18120606 - Trần Thị Trang
- 18120609 - Hồ Khắc Minh Trí (Nhóm trưởng)
- 18120634 - Nguyễn Lê Anh Tuấn

# Đề bài

## Mô tả dữ liệu

- Mô tả ý nghĩa các thuộc tính của các nguồn dữ liệu sau (chỉ cần mô tả các thuộc tính cần thiết cho đồ án):
  - Dữ liệu UK Car Accidents 2005 - 2015 (SV chỉ lấy dữ liệu 3-4 năm, hoặc lấy dữ liệu từ 2011-2014 được cung cấp sẵn):
    https://www.kaggle.com/silicon99/dft-accident-data/discussion/28970?fbclid=IwAR1BvAiy8mEMy01XXAKtxLkX7Kx3kwPt3c3EYhwoxlWq5psikSAB2mVlF8A
  - Dữ liệu LSOA-Postcode mapping:
    https://geoportal.statistics.gov.uk/datasets/postcode-to-output-area-to-lower-layer-super-output-area-to-middle-layer-super-output-area-to-local-authority-district-august-2021-lookup-in-the-uk/about
  - Dữ liệu UK-Postcodes:
    https://github.com/academe/UK-Postcodes/blob/master/postcodes.csv

## Thiết kế kho dữ liệu (KDL), tổng hợp, nạp dữ liệu các nguồn vào KDL và thiết:

- Mapping các nguồn dữ liệu trên để lấy giá trị xây
  dựng Geography dimension với phân cấp chiều như sau: Country > Region > County > Town City.
- Chuyển đổi dữ liệu ngày tháng sao cho có thể tạo được Date dimension với phân cấp chiều: Year > Quarter > Month > Day.
- Xác định và thiết kế các phân cấp chiều khác để đáp ứng yêu cầu OLAP và Report.

## OLAP và Report:

1. Thống kê số lượng nạn nhân theo Mức Độ Nghiêm Trọng ở các Địa phương trong tất cả các năm.
2. Thống kê số lượng nạn nhân theo Mức Độ Nghiêm Trọng ở các Địa Phương theo các Quý trong từng năm.
3. Thống kê số lượng người tử vong theo Giới Tính, Loại Nạn Nhân và Nhóm Tuổi theo các năm.
4. Thống kê số lượng TNGT theo Mức Độ Nghiêm Trọng và Thời Điểm Trong Ngày (Morning: 5am-12pm, Afternoon: 12pm-5pm, Evening: 5pm-9pm, Night: 9pm-5am) trong các năm.
5. Thống kê số lượng TNGT theo Mức Độ Nghiêm Trọng, Vùng, và Kiểu Đường trong các năm.
6. Thống kê số lượng nạn nhân theo Mức Độ Nghiêm Trọng, Loại Nạn Nhân (Casualty Type) và Độ Tuổi trong các năm, Độ Tuổi được định nghĩa như sau:

- Children: 0-15
- Young adult: 0-17
- Adult: 18-59
- 60 and over: 60-...

7. Tổng hợp số lượng tai nạn theo Mục Đích Hành Trình và Loại Phương Tiện.
8. Tạo thêm thuộc tính Built-up Road trong table Accidients. Built-up Road có 2 giá trị:

- Built-up road: Nếu tốc độ giới hạn (Speed Limit) dưới 50 mph.
- Non Built-up road: Nếu tốc độ giới hạn từ 50 mph.

9. Thống kê số lượng tai nạn theo Mức Độ Nghiêm Trọng, Loại Phương Tiện, Built-up Road trong các năm.
10. Sinh viên tự thiết kế những bảng thống kê khác để có thêm nhiều chiều đánh giá TNGT ở UK.
11. Định nghĩa fact Variance để tính mức độ tăng giảm của TNGT theo đơn vị phần trăm qua các năm.
12. Xây dựng đồ thị/ biểu đồ cho các bảng thống kê ở trên.
13. Dùng regional map để biểu diễn trực quan (bằng màu sắc) số lượng TNGT ở các vùng trong năm.

## Data Mining: Gợi ý

- Sử dụng mô hình dự đoán mức độ nghiêm trọng của các tai nạn.
- Sinh viên có thể đề xuất ứng dụng một trường hợp bất kỳ, lý giải thuật toán sử dụng, vì sao, kết quả như thế nào,…

## Một số hình ảnh kết quả đồ án:

### NDS (Normalize Data Store)

![NDS](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/NDS.png)

### DDS (Dimensional Data Store)

![DDS](https://res.cloudinary.com/minhtri2404/image/upload/v1643539209/TTKD-12-BI-Project-UKAccidents/DDS.png)

### OLAP (Online Analytical Processing)

![OLAP](https://res.cloudinary.com/minhtri2404/image/upload/v1643539209/TTKD-12-BI-Project-UKAccidents/OLAP01.png)
![OLAP](https://res.cloudinary.com/minhtri2404/image/upload/v1643539209/TTKD-12-BI-Project-UKAccidents/OLAP02.png)

### MDX (Multidimensional Expressions)

![MDX](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/MDX01.png)
![MDX](https://res.cloudinary.com/minhtri2404/image/upload/v1643539209/TTKD-12-BI-Project-UKAccidents/MDX02.png)

### Data Visualization

![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539209/TTKD-12-BI-Project-UKAccidents/v_Cau01.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau02.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau03.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau04.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau05.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau06.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau07.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau09.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau11.png)
![DataVisualization](https://res.cloudinary.com/minhtri2404/image/upload/v1643539200/TTKD-12-BI-Project-UKAccidents/v_Cau13.png)

### Data Mining

![DataMining](https://res.cloudinary.com/minhtri2404/image/upload/v1643540758/TTKD-12-BI-Project-UKAccidents/DataMining01.png)
![DataMining](https://res.cloudinary.com/minhtri2404/image/upload/v1643540758/TTKD-12-BI-Project-UKAccidents/DataMining02.png)
![DataMining](https://res.cloudinary.com/minhtri2404/image/upload/v1643540758/TTKD-12-BI-Project-UKAccidents/DataMining03.png)
![DataMining](https://res.cloudinary.com/minhtri2404/image/upload/v1643540758/TTKD-12-BI-Project-UKAccidents/DataMining04.png)
