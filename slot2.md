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
- sếp của dân QC/Tester, thường đi lên từ QC/Tester
- nhiệm vụ của Test Manager là:
    - phối hợp với PM (Project Manager) để cùng tham gia vào các công đoạn kiểm thử phần mềm, để lên kế hoạch kiểm thử ap
    - phân bổ nhân lực, QC/Tester nào sẽ test dự án/module/chức năng nào
    - để xuất mua những trang thiết bị/ tài nguyên cần thiết hỗ trợ cho việc kiểm thử 
    - bàn thảo với PM về hiện trạng bug 
### 3.4 USER, END-USER
- Người dùng, người dùng cuối là chốt chặn cuối cùng của công việc kiểm thử phần mềm
- Họ sẽ dùng thử/thật app và cho feedback/phản hồi rằng app xài đc cho công việc
của hoặc app kông giúp ích gì haocwj app nên cải tiế thêm tính năng gì để dùng phù hợp 
- Việc người dùng cuối/user dùng app rồi chấp nhận nó đưa nó vào trong công việc hàng ngày - còn gọi là NGHIỆM THU SẢN PHẨM - UAT - USER ACCEPTANCE TESTING
- có 2 loại app (nhìn theo góc độ phổ biến cho user)
    - GENERIC APP (app dành cho số đông, app phổ thông, tool tiện ích)
        + EX: Game, Cococ, firefox, word, excel, photoshop : app viết cho nhiều người dùng
            + có phiên bản download trên mạng, hoặc dùng thử online 
            + dùng thử trải nghiệm, feedback, send bug report
            + đưa ra nhiều phiên bản khác nhau tùy từng giai đoạn làm app để collect bug/feedback
                + các phiên bản: Alpha, Beta, RC (Release Candidate), Preview, Stable/LTS, Nightly Build, Development Build(phiên bản thử nghiệm của dân dev công bố sớm cho thiên hạ)
    - CUSTOM APP/CUSTOMIZED APP/BE-SPOKE APP ( app đc viết riêng cho nhu cầu của ai đố, app đặc chế cho ai đó)
        + EX: App quản lí ngân hàng TPBank, App quản lí tồn kho, bán hàng của TGDD : app viết riêng cho nhu cầu của ai đó, đơn vị nào đó 
            + không có download, viết xong bàn giao ngay cho chính chủ đặt hàng 
            + Dev team nghĩ rằng đã đến lúc cài đặt cho khách hàng dùng thử user chính là nhân viên của các công ty đặt hàng làm app sẽ xài thử trong công việc của họ
            + cô thu ngân, dùng thử tính năng tính tiền ...
            + cô giao dịch viên, dùng thử tính năng quản lí sổ tiết kiệm  
            + cho feedback...
    


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


# II. 7 viên ngọc rồng - 7 NGUYÊN LÍ CỦA KIỂM THỬ PHẦN MỀM - 7 PRINCIPLES OF SOFTWARE TESTING 
## 1. TESTING SHOWS THE PRESENCE OF DEFECTS
- kiểm thử phần mềm là tìm bug/tìm sai sót của app của quá trình làm app
- Bug luôn tồn tại trong app dù test kĩ cỡ nào !! có app là có bug/còn bug
- nhiệm vụ của kiểm thử là tìm mọi cách/ cố gắng lôi ra càng nhiều bug càng tốt, càng nhiều bug nghiêm trọng càng tốt!!!
- Lập trình viên phải có trách nhiệm viết code tử tế QC, phải test với trách nhiệm cao nhất, không xảy ra bug nghiêm trọng vì ta cần phải dữ uy tín với khách hàng 
## 2. EXHAUSTIVE TESTING IS NOT POSSIBLE
- Dân QC ko thể test hết các khả năng/ các tình huống xài app của user
- dân QC ko thể mô phỏng/ giả lập/ dự đoán hết các hành vi sử dụng app của user để ngăn chặn những bug họ có thể gặp trong tương lai xài app 



## [NGOẠI TRUYỆN]
- bàn về những con số gắn với kiến thức lập trình
- OOP: 4   +  5    
    AEIP    SOLID
- AGILE: 4   +   12
    tuyên ngôn   nguyên lí
- DATABASE: 
    - 3 loại SQL
        + DDL: create/drop
        + DML: select/update/delete
        + DCL(Data Control Language): grant/revoke
    - 3 loại dạng chuẩn phổ biến
        + 1NF, 2NF - Normaliztion Form - kĩ thuật đánh giá việc thiết kế ERD/Table tốt hay không ?
- DESIGN PATTERNS: 
    - 23 thiết kế chuẩn về các class cần có cho những bài toán quen thuộc nào đó 
- SOFTWARE TESTING:
- SWR302: 3 góc nhìn - why, what, who 
