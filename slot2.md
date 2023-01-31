# 1. Show bug 
- nút send của apple design sai pixel 
- bug của rufus (update verion mới)
    - ["change log"]() -> tester -> log bug (bug zilla)
    - fix bug, sửa ver cũ nếu hoạt động như shit 

# 2. bug ra đời như thế nào 
- khái niệm bug hình thành khi con bọ bay vào máy nghe nhạc của thomas edison 
- con bug liên quan đến máy tính là một con bọ bay vào trong máy tính 

# MAIN LESSON
## I. GIẢI THÍCH MỘT SỐ THUẬT NGỮ KIỂM THỬ PHẦN MỀM - SOFTWARE TESTING TERMS / TERMINOLOGIES 
## 1. Ý nghĩa của từng từ bug/defect/error/mistake/failure: xem câu huyền thoại trong Cheat Sheet
- tạm hiểu phần mềm được viết ra sẽ có những thừ không như mong đợi 
    - chạy/ xử lý không ổn, kết quả không chính xác như mong đợi 
    - việc hiện thực cài đặt code/impement không theo như thiết kế ban đầu, app không dùng được trong thực tế 
## 2. Định nghĩa kiểm thử phần mềm là gì??
-  là hoạt động nhằm tìm kiếm và phát hiện ra các lỗi của phần mềm, đảm bảo phần mềm chính xác, đúng và đầy đủ theo yêu cầu của khách hàng, yêu cầu của sản phẩm đã đặt ra
- So Sánh xem app được implement, cài đặt, hiện thực có giống như thiết kế hay không 
    - Quy trình làm phần mềm thì Requirement, Design (UI/DB, MVC, DAO) được gom vào trong 1 tài liệu/document đc gọi là SPECIFICATION ["bản đặc tả phần mềm"]()  
    - Căn cứ theo bản SPECIFICATION để xem nhóm Developer có cài đặt các màn hình của app có đùng như thiết kế ko
- So Sánh Xem APP có đảm bảo được cá tiêu chí/ hiệu năng vận hành hay không??? đảm bảo đc các NON-FUNCTIONAL REQUIREMENTS HAY KHÔNG ?
    - kiểm thử trên các NON-FUNCTIONAL REQS, đo xem hiệu năng vận hành của app
    - tốc độ xử lí đủ nhanh?
    - khả năng chịu tải/khả năng xử lí bao nhiêu request, bao nhiêu user trong 1 thời điểm bất kì 
    -  PERFORMANCE TESTING 
    > giả lập lượng tải (1000 users, 5000 request...) lên app/server
    >> xài tool: <kbd>JMETER</kbd> (giả lập n user, gửi n request, nhận về response cho từng request, đo thời gian phản hồi, vẽ biểu đồ..)
- So sánh giữa ["EXPECTED"]() vs ["ACTUAL"]() 
    + <kbd>EXPEACTED</kbd> : kì vọng, phần mềm đáng ra phải như thế này
    + <kbd>ACTUAL</kbd> : thực tế, nhưng thực tế nó là thế này 
        + expected == actual -> true
        + expected != actual -> false
* ["Ví Dụ"](): Môn Java Web, phần login 
    - login thành công, màn hình sau login phải chào Hello<fullname>
    - chạy app, login account hoangnt -> thành công, expected lời chào phải là: Hello hoàng ngọc trinh
    - thực tế khi chạy app (code bạn viêt) mà nó lại chào Hello hoangnt 

- tính toán trước kì vọng ->  EXPECTED 
- so sánh kì vọng với ->  ACTUAL 

## 3. Ai tham gia vào quá trình kiểm thử phần mềm ?
### 3.1 DEVELOPER
- [Ngoại Truyện] 
    - Coder  -  Programmer - Developer - Software Engineer   
### 3.2 TESTER/QC/QA
### 3.3 TEST MANAGER
### 3.4 USER, END-USER


## [NGOẠI TRUYỆN - HỌC CHI TIẾT HƠN Ở BÊN SWR]
- SOFTWARE REQUIREMENTS: có 2 loại lớn, có 2 loại reqs phổ biến
- ["FUNCTIONAL REQUIREMENTS"]() - YÊU CẦU CHỨC NĂNG
    - ["Ví Dụ"]() 
        - app hỗ trợ việc ["LƯU"]() hồ sơ, bệnh án của bệnh nhân (app QLBV)
        - app cung cấp cho customer tính năng ["THEO GIÕI"]() trạng thái đơn hàng (app BH)
        - app cung cấp cấp tính năng ["TÍNH ĐIỂM"]() cho người mua hàng ở quầy thu ngân (7-E)
    - ["kết:"]()
        - câu phát biểu về tính năng/tên màn hình/chức năng của app cung cấp cho người dùng làm đc 1 việc gì đó gọi là FUNCTIONAL REQ -> VERB + OBJECT 
- ["NON-FUNCTIONAL REQUIREMENTS"]() - YÊU CẦU PHI CHỨC NĂNG (yc mà không focus vào 1 chức năng cụ thể nào đó)
    - ["Ví Dụ"]() 
        - App phải dễ dùng, màu sắc hài hòa(mơ hồ)
        - Các xử lí của app (nhấn nút bấm) thì phản hồi kết quả trong vòng <= 3s 
        - App có khả năng hỗ trợ tối đa 10k người dùng cùng lúc trong giờ cao điểm X với thời gian phản hồi 1 request từ 1...15s
    - ["kết:"]()
        - Câu phát biểu liên quan đến cảm xúc, trải nghiệm khi xài app, khi xài 1 tính năng bất kì (ko focus vào 1 tính năng cụ thể focus vào 1 tính năng cụ thể - focus vào trải nghiệm app nói chung - NON) ADJECTIVE/ADVERB: từ diễn tả tính chất!!!
        App phải dễ dùng, xài đã, tiện lợi, an toàn, bảo mật, an tâm, nhanh chậm đẹp xấu to nhỏ.