Project: ẢNH HƯỞNG CỦA CÁC KỸ THUẬT TIỀN XỬ LÝ TRONG BÀI TOÁN PHÁT HIỆN BỆNH TRÊN ẢNH X-QUANG NGỰC

Tóm tắt sơ lược bài toán:
	- Thực hiện các kỹ thuật tiền xử lý trên bộ data VinDr CXR.
	- Chạy mô hình để kiểm tra kết quả của các kỹ thuật tiền xử lý.
	- Đưa ra kết luận cho bài toán.

Data:
	- Notebook "Image Enhancement" thực hiện các kỹ thuật tiền xử lí: tăng cường độ tương phản (histogram equalization), khử nhiễu (bilateral filter), biến đổi phân ngưỡng (thresholding transformations), tạo hiệu ứng viền (unsharp masking).
	- Notebook "Split datat" thực hiện chia dữ liệu trên tập test gốc.
	- Link data: https://tinyurl.com/XLAKY-Group4-Data

Model: 
	- Faster R-CNN: là một mở rộng của phương pháp R-CNN và Fast R-CNN trong việc phát hiện đối tượng. Phương pháp R-CNN ban đầu yêu cầu thực hiện truyền thuận của Mạng Neural Tích chập cho mỗi khoảng 2000 đề xuất vùng trong một hình ảnh. Fast R-CNN đã cải thiện điều này bằng cách chia sẻ tính toán đặc trưng tích chập giữa các đề xuất khác nhau, giúp tăng tốc quá trình phát hiện.
	-YOLOv5: được phát hành vào năm 2020 bởi Ultralytics, một mô hình thị giác máy tính dùng để phát hiện đối tượng. YOLOv5 đã thực hiện một số thay đổi kiến trúc, đáng chú ý nhất là việc chia mô hình thành ba thành phần, bao gồm backbone, neck và head.
Đầu tiên, Backbone của YOLOv5 là Darknet53, một kiến trúc mạng được thiết kế để trích xuất đặc trưng. Nó sử dụng cửa sổ filter nhỏ và kết nối dư để tăng cường khả năng. 
Neck của YOLOv5, chịu trách nhiệm kết nối giữa backbone và head. Nhiệm vụ của neck là tập hợp và tinh chỉnh các đặc trưng được trích xuất bởi backbone. Kiến trúc bao gồm mô-đun Spatial Pyramid Pooling (SPP) và CSP-Path Aggregation Network .
Head của YOLOv5 bao gồm ba nhánh dự đoán khác nhau về các đặc trưng và thông tin về các đối tượng trong ảnh đầu vào. Cụ thể, các nhánh này dự đoán bounding boxes, xác suất các lớp và confidence scores cho các đối tượng.
Trong báo cáo này, chúng tôi sử dụng phiên bản YOLOv5l để tiến hành huấn luyện.
	- YOLOv8 là phiên bản mới nhất của mô hình phát hiện đối tượng YOLO, được phát hành vào tháng 1 năm 2023 bởi Ultralytics.
YOLOv8 có cùng backbone với YOLOv5 nhưng có một số thay đổi trên CSPLayer, hiện được gọi là C2f module. 
YOLOv8 sử dụng mô hình không gắn kết (anchor-free) với kiến trúc Head tách rời để xử lý độc lập các nhiệm vụ về objectness, classification, và regression.
Các hàm mất mát trong YOLOv8 bao gồm CIoU (Complete Intersection over Union) và DFL (Distribution Focal Loss) cho việc mất mát bounding box và mất mát phân loại nhị phân. 
Trong báo cáo này, chúng tôi sử dụng phiên bản YOLOv8l để tiến hành huấn luyện.

Cách chạy model:
	Faster RCNN: 
		- Upload hai notebook "FasterRCNN" và "Metric4FasterRCNN" lên kaggle và mở trên kaggle.
		- Add data cần thiết VinDR-CXR-normal:
			+ Normal: https://www.kaggle.com/datasets/ngccaonhduy/vindr-cxr-normal
			+ Process 1 - 5: https://www.kaggle.com/datasets/ngccaonhduy/vindr-cxr-processX (thay đổi X từ 1 đến 5)
		- Chỉnh các path data trong notebook theo từng process muốn train.
		- Run all.

	YOLO:
		- Tạo shotcut vào MyDrive: https://tinyurl.com/XLAYKYOLOmodel
		- Vào đường dẫn: Project -> Working. Chạy các mô hình tương ứng với từng loại data.
		- Tất cả code đã được hiệu chỉnh để có thể chạy mà không thay đổi gì.


	



