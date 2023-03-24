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



===============================================================================================================================================================================



# II. 7 viên ngọc rồng - 7 NGUYÊN LÍ CỦA KIỂM THỬ PHẦN MỀM - 7 PRINCIPLES OF SOFTWARE TESTING 
## 1. TESTING SHOWS THE PRESENCE OF DEFECTS
- kiểm thử phần mềm là tìm bug/tìm sai sót của app của quá trình làm app
- Bug ["luôn tồn tại trong app"]() dù test kĩ cỡ nào !! có app là có bug/còn bug
- nhiệm vụ của kiểm thử là tìm mọi cách/ cố gắng lôi ra càng nhiều bug càng tốt, càng nhiều bug nghiêm trọng càng tốt!!!
- Lập trình viên phải có trách nhiệm viết code tử tế QC, phải test với trách nhiệm cao nhất, không xảy ra bug nghiêm trọng vì ta cần phải dữ uy tín với khách hàng 
## 2. EXHAUSTIVE TESTING IS IMOSSIBLE
- Dân QC ko thể test hết các khả năng/ các tình huống xài app của user
- dân QC ko thể mô phỏng/ giả lập/ dự đoán hết các hành vi sử dụng app của user để ngăn chặn những bug họ có thể gặp trong tương lai xài app 

- Ví Dụ: TEST APP CALCULATOR CỦA WINDOWS, TEST CHỨC NĂNG + - * /
    + cần phải test :
        - 2 số nhỏ coi có đúng không ?
        - 2 số, 1 số nhỏ, 1 số lớn cọi có đúng không ?
        - 2 số mà có khả năng 
        - 2 số dương và âm 
        - 2 số âm ...

    + DO KHÔNG TEST HẾT KHẢ NĂNG XÀI APP DO ĐÓ VỀ LÍ THUYẾT VẪN CÓ THỂ TIỀM ẨN BUG DO RƠI VÀO TÌNH HUỐNG TA CHƯA TEST KỊP, MÀ ĐỂ TEST HẾT THÌ TÍNH NĂNG 
    TRIỆU NĂM 
    + PHẢI CÓ KĨ THUẬT NÀO ĐÓ, CHÁC THỨC NÀO ĐÓ ĐỂ KHÔNG TEST HẾT CÁC TÌNH HUỐNG XÀI APP CỦA USER MÀ VẪN KẾT LUẬN/VẪN CÓ THỂ RELEASE SẢN PHẨM
## 3. EARLY-TESTING
- kiểm thử càng sớm càng tốt, thậm chí ngay cả khi chưa viết code thì dân qc cũng đã phải tham gia vào quá trình kiểm thử bằng cách review các tài liệu,
  Requirements. Design 
    + Dân QC sẽ giao tiếp luôn với dân BA để hiểu hệ thống từ sớm, có thể đề xuất ...
    + thêm 1 góc nhìn của người sẽ giúp việc phân tích requirements, design thêm chính xác
## 4. DEFECTS CLUSTERING - SỰ PHÂN BỐ/SỰ TẬP TRUNG CỦA BUG
- BÀN về sự phân bố/ sự tập trung của 1 thứ gì đó, người ta hay nhắc đến nguyên lí 80/20 - nguyên lí Pareto - bàn về sự tập trung, tỉ trọng của những thứ 
  quan trọng: 20% thời gian bỏ ra mà đạt được 80% kết quả -> tốt về mặt quản lí 

- Nhìn trong kiểm thử phẩn mềm cũng có nguyên lí này: bug thường tập trung hay xuất hiện nhiều ở một số chỗ, xuất hiện ít ở chỗ khác 
    + App mà có sử dụng các thiết bị ngoại vi: camera, sensor, máy đọc thẻ
    + App mà có kết nối với app khác, ví dụ lazada kết nối với momo, và các ví thì thường những chỗ kết nỗi này hay có bug, hay bị trục trặc
        - do tính ổn định, tương thích, khả năng hoạt động chính xác của thiêt bị 
        - timeout do đường truyền và độ trễ xử lí của app bên ngoài
## 5. PESTICISE PARADOX - NGHỊCH LÍ THUỐC TRỪ SÂU!!! HIỆN TƯỢNG KHÁNG THUỐC 
- Phun thuốc trừ sâu để tiêu diệt sâu, nhưng sâu không chết
- Nhờ dân QC test app, nhưng lại để sót bug, bug nghiêm trọng, bug ngớ ngẩn vẫn tồn tại, QC không đóng tròn vai trò gác cổng chất lượng 
- QC chủ quan do làm đi làm lại, test đi test lại một chức năng quen -> chủ quan, ví dụ khi tuần trước đã test phần CRUD product rồi, ổn, tuần này test chức năng
  Order, do dân dev có sửa tùm lum code, nhưng chủ quan nghĩ rằng phần Product đã ổn, không cần test lại, chỉ tập trung test Order, chủ quan này có thể trả giá phần
  Product
    + giải pháp: Dân QC nên được bố trí, hoán đổi công việc/project/module kiểm thử trong 1 khoảng thời gian nào đó
        - test Mobile app 6 tháng, 6 tháng sau chuyển qua test web app vẫn cùng app nhưng khác môi trường, khác môi trường thì tọa sự tò mò khám phá, tránh đc nhàm chán
        lặp lại công việc 
## 6. CONTEXT DEPENDENT - KIỂM THỬ PHỤ THUỘC NGỮ CẢNH
- Loại app khác nhau (web, mobile, desktop)
- Loại môi trường / platform/ OS khác nhau
- thiết bị khác nhau 
- thì phải có cách test khác nhau !!!
## 7. ABSENCE OF ERRORS FALLACY - ảo tưởng, quan niệm sai về việc app ít bug
- không gáy về việc app ít bug . app ít bug không phải là đáng tự hào 
- đừng ảo tưởng rằng app ít bug là app ngon 
- Việc viết app, làm app phải nhắm đến việc tạo ra giá trị cho người dùng nó .

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



=================================================================================================================================================================================


TESTING LEVEL - 4 MỨC ĐỘ KIỂM THỬ
- quá trình viết app bắt đầu từ REQUIREMENTS 
            ...giai đoạn khác...
                  implementation gia đoạn viết code làm app
- XÉT RIÊNG GIAI ĐOẠN VIẾT CODE - LÀM APP - IMPLEMENTATION CÁC REQUIREMENTS
THÌ VIỆC HOÀN THIỆN APP, VIẾT CODE SẼ LÀM 4 BƯỚC
* LEVEL 1 - mức 1: developer vừa viết xong hàm, hoặc class (chứa hàm/method bên trong) 
    - class UserDTO, class DBUtil
    # MỨC ĐƠN VỊ - UNIT LEVEL
    - code vừa viết xong mức đơn vị, tức là hàm/ class vừa xong, phải đảm bảo hàm class xử lí ngon, chính xác thông tin 
    - hàm() phải được test xem nhận đầu vào xử lí trả kết quả có đúng không
    - class phải được test xem nhận đầu vào qua constructor, setter, trả về kết quả có đúng không qua getter, toString() và các lệnh return 

* LEVEL 2 - mức 2: developer bắt đầu xây dựng các class phức tạp - phối hợp các class khác nhau + font-end để hình thành nên các chức năng đơn lẻ  
    # MƯC TÍCH HỢP - INTEGRATION LEVEL 

* LEVEL 3 - SYSTEM LEVEL
* LEVEL 4 - ACCEPTANCE LEVEL

====================================================
# UNIT TESTING LEVEL - LÀ CÁCH MÀ DÂN DEV SẼ TEST CODE CỦA MÌNH !!! TEST HÀM VÀ CLASS
- làm sao/ kĩ thuật nào để test code/test hàm/ test class của mình ?
- có những kĩ thuật sau để làm unit test

1. In kết quả xử lí của hàm/method ra màn hình 

2. in kết quả xử lí của hàm ra log file, .txt file

3. pop-up lên desktop, trình duyệt

4. ngầu nhất: dùng 1 bộ thư viện trợ giúp quá trình kiểm thử hàm/class mà không cần in ra kết quả xử lí của hàm, c  hỉ dùng 2 tín hiệu xanh-đỏ
dùng 1 bộ thư viện phụ trợ - còn gọi là unit test framework
- Unit test, Unit Test framework liên quan đến một vài khái niệm quan trọng sau
    + CI (là 1 phần đầu của tiến trình CI/CD/DevOps) - Continuous Integration - Tích hợp liên tục
    + TDD - Test Driven Development
    + DDT - Data Driven Testing 

================================================================================================================
UNIT TEST NOIS CHUNG, JUIT NÓI RIÊNG DÙNG MÀU SẮC XANH ĐỎ ĐỂ QUY ƯỚC CHO HÀM ĐÚNG HAY SAI 
- XANH : VIỆC SO SÁNH GIỮA EXPECTED VÀ ACTUAL THẤY == NHAU
  Hàm xử lí kết quả và trả về như kì vọng, 5! đúng là trả về 120 thiệt khi xài hàm 
- ĐỎ : VIỆC SO SÁNH GIỮA EXPECTED VÀ ACTUAL THẤY KHÁC NHAU, != NHAU
  HÀM XỬ LÍ KẾT QUẢ TRẢ VỀ KHÁC KÌ VỌNG!!!
  CÓ 2 KHẢ NĂNG XẢY RA HERE!!!
  - Hàm đúng kì vọng sai
  - Hàm sai kì vọng đúng 

- MỘT CLASS KIỂM THỬ LẠI CHỨA NHIỀU TEST CASE, CHỨA NHIỀU SO SÁNH XANH ĐỎ, QUY TẮC XANH ĐỎ TỔNG THỂ NHƯ SAU: 
    - XANH TỔNG: TẤT CẢ CÁC TEST CASE, CÁC HÀM SO SÁNH PHẢI XANH HẾT, THÌ MỚI GOM LẠI THÀNH 1 CÁI XANH CHUNG, XANH TỔNG 
- ĐỎ TỔNG: CHỈ CẦN 1 THẰNG TEST CASE BỊ ĐỎ, TOÀN BỘ BỊ ĐỎ
    - CHỈ CẦN 1 THẰNG TEST/ SO SÁNH MÀ CÓ EXPECTED != ACTUAL -> ĐỎ -> HÀM CÓ VẤN ĐỀ

lí do 1 thằng đỏ cả đám đỏ 
- HÀM NẾU ĐÃ ĐƯA VÀO TEST THÌ PHẢI ĐÚNG HẾT, XANH HẾT 
- HÀM NẾU CÓ ÍT NHẤT 1 ĐỎ, HÀM TÍNH TOÁN KO ỔN ĐỊNH, KO CHÍNH XÁC




============================================================================================================================================
NHẬP MÔN CI - CONTINOUS INTEGRATION NÓ LÀ PHẦN KHỞI ĐẦU CỦA QUY TRÌNH CI/CD/DEVOPS
- chuẩn bị sẵn Github acc, url nên sửa toàn là chữ thường 
QUY TRÌNH ĐÓNG GÓI APP!!! >.JAR, .WAR .APK SETUP.EXE 
