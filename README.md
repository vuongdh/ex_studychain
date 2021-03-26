# GIOI THIEU
## Project gom 3 phan chinh
- certificate-network: Chứa cấu hình của mạng, chaincode,...
- academy-app: ứng dụng phía Academy Org
- student-app: ứng dụng phía Student Org

# CHAY PROJECT
## Setup network va cai dat chaincode
## Pull Docker Image
- curl -sSL https://bit.ly/2ysbOFE | bash -s -- 2.0.0 1.4.4 0.4.18
- cp -r fabric-samples/bin ./
- cd network
- - Up network: ./network.sh up
- - Down network: ./network.sh down
## Phia Client
- cd client
- npm install
- npm start
## Phia Server
- cd server
- npm install
- npm start

# CHU Y
Ở thời điểm khởi tạo chaincode, vẫn chưa có gì được lưu trong chaincode.

Phía Academy có các quyền:

- Register giảng viên mới
- CreateSubject, chỉ có admin mới có quyền này
- CreateScore, nếu một student và một subject đã tồn tại trong ledger
- CreateCertificate: nếu một student đã hoàn thành tất cả các subject thì mới có thể cấp certificate
- QuerySubject, Student, Score, Certificate
- GetAllSubjects, Students, Scores, Certificates

Phía Student có các quyền:
- Register student mới
- GetStudent, Score, Certificate của chính mình
- GetAllSubjects
(Các câu lệnh xem thêm trong README.md của từng thư mục)

Xem các structure trong certificate-network/database/academy/go/certificate.go để hiểu rõ hơn.
