# ẢNH HƯỞNG CỦA CÁC KỸ THUẬT TIỀN XỬ LÝ TRONG BÀI TOÁN PHÁT HIỆN BỆNH TRÊN ẢNH X-QUANG NGỰC

## Giới thiệu
Trong sự phát triển mạnh mẽ của trí tuệ nhân tạo, việc ứng dụng các kỹ thuật học máy, học sâu đóng vai trò quan trọng trong chẩn đoán bệnh trên hình ảnh X-Quang, điều này giúp phát hiện sớm và điều trị kịp thời cho các bệnh nhân. Bên cạnh các thuật toán, việc tiền xử lý hình ảnh trước khi huấn luyện cũng ảnh hưởng đáng kể đến hiệu suất. Do đó, ở bài toán này, chúng tôi tiến hành thực nghiệm để kiểm tra mức độ hiệu quả của một số phương pháp tiền xử lý hình ảnh cơ bản như tăng cường độ tương phản (histogram equalization và CLAHE), khử nhiễu (bilateral filter), biến đổi phân ngưỡng (thresholding transformations), tạo hiệu ứng viền (unsharp masking) trên bộ dữ liệu VinDr CXR với ba mô hình: YOLOv5, YOLOv8 và Faster R-CNN. VinDr CXR là bộ dữ liệu X-quang ngực của Việt Nam do VinDr lab nghiên cứu và công bố vào cuối năm 2020. Đây là một trong số ít các bộ dữ liệu về X-quang có đánh dấu các vị trí bất thường và được thực hiện bởi nhiều bác sĩ chuyên khoa có kinh nghiệm, vì vậy đây là bộ dữ liệu đáng tin cậy để tiến hành thực nghiệm. Kết quả thực nghiệm cho thấy các phương pháp tăng cường ảnh cơ bản không mang lại hiệu quả cho mô hình.

## Dataset
Bộ dữ liệu VinDR-CXR đã được giới thiệu vào cuối năm 2020. Bộ dữ liệu này bao gồm hơn 100.000 hình ảnh định dạng DICOM được thu thập từ năm 2018 đến năm 2020 tại Bệnh viện 108 và Bệnh viện Đại học Y Hà Nội. 17 bác sĩ chuyên khoa đã gắn nhãn cho các hình ảnh với ít nhất 8 năm kinh nghiệm. Các tác giả đã xây dựng bộ dữ liệu này cho VinBigData Chest X-ray Abnormalities Detection Competition https://www.kaggle.com/c/vinbigdata-chest-xray-abnormalities-detection/ trên nền tảng Kaggle. Bộ dữ liệu cho cuộc thi bao gồm 18.000 hình ảnh với 15 nhãn, bao gồm một tập huấn luyện gồm 15.000 hình ảnh và một tập kiểm tra gồm 3.000 hình ảnh. Ba bác sĩ đã gán nhãn cho các hình ảnh trong tập huấn luyện, trong khi năm bác sĩ đã gán nhãn cho tập kiểm tra.

## Các phương pháp tiền xử lí
### Histogram equalization
![His eq](https://github.com/the-ntg/Chest-X-rays-object-detection/assets/109457460/127130f0-18e0-4211-bbb7-30f42fb64f8a)

### CLAHE
![CLAHE](https://github.com/the-ntg/Chest-X-rays-object-detection/assets/109457460/e4dd407a-593d-4f7d-a3be-0bb7739f950b)

### Bilateral Filtering
![BiFi](https://github.com/the-ntg/Chest-X-rays-object-detection/assets/109457460/9b7143f3-b11f-4806-97e8-6bcfec9de3dd)

### Unsharp masking
![UnMa](https://github.com/the-ntg/Chest-X-rays-object-detection/assets/109457460/dac6b89e-0295-43c2-a05e-572648705c29)

### Thresholding Transformations
![Threshold](https://github.com/the-ntg/Chest-X-rays-object-detection/assets/109457460/ba007507-c0cd-4ef3-a056-8dadf1caafff)


## Model Performance
Chúng tôi xử dụng các mô hình bao gồm : Yolov5, Yolov8 ,và Faster R-CNN để thực hiện thí nghiệm với các bộ dữ liệu sau : 
|Data | Phương pháp xử lí |
|--------------|----------|
| Normal | Không xử lí | 
| Process 1 | CLAHE |  
| Process 2  | Bilateral Filtering | 
| Process 3  | Unsharp masking | 
| Process 4  | Thresholding Transformations |
| Process 5  | Histogram equalization |


Kết quả đạt được như sau :

![image](https://github.com/the-ntg/Chest-X-rays-object-detection/assets/109457460/d16c381a-3a33-4444-bc17-48610954f9a6)



## Contact
Authors:
Ngo Huynh Truong, Tinh Pham Phuc Do, Ngoc Dinh Duy Cao, The Tran Gia Nguyen

Faculty of Information Science and Engineering, University of Information Technology, Ho Chi Minh City, Vietnam

Vietnam National University, Ho Chi Minh City, Vietnam

{20522085,20522020,20521661,20521940}@gm.uit.edu.vn
