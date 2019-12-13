# Documentation cho dự án thuộc Masso Corp

Masso là công ty...

## Giới thiệu
Các dự án của công ty masso được thực hiện phục vụ đưa ra các giải pháp dành cho người sử dụng và bán hàng online. Các dự án ở thời điểm viết documentation được sử dụng lõi là vue.js cho phía client và node.js cho phía server. Việc mô tả lại toàn bộ hệ thống giúp bạn nắm bắt một cách tổng quan nhất. Điều này không đồng nghĩa với việc sẽ đi hết được toàn bộ các phần của dự án.

### Lộ trình documentation

#### 🎍Tổng quan
✅ Tổng quan về các công nghệ mà công ty masso sẽ sử dụng ở trong các dự án. <br />
✅ Tìm hiểu về các làm việc của Git và các thủ thuật khi làm việc với Git một cách dễ dàng hơn. <br />
----- ✅ Git hoạt động như thế lào :D  <br />
----- ✅ GIải thích về một git follow đơn giản (đề xuất công ty nên sử dụng, phù hợp với team 5-6 người) <br />
----- ✅ Sơ bộ về cách quy định về một commit, giúp quản lý commit cho dự án một cách tốt hơn. <br />
----- ✅ Cách xử lý nếu bị conflict, merge commit, xử lý confict branch. <br />

#### 😜 Vue documentation 
✅ TÌm hiểu về vue. <br />
⬜ Các kiến thức nền cần biết tối thiểu để thực hiện các dự án hoặc các task ban đầu: <br />
----- ✅ Xử lý components (f1a) <br />
----- ✅ Cách code scss theo quy tắc BEM (f2a) <br />
----- ✅ Cách sử dụng axios để giao thức với API (f3a) <br />
----- ✅ Cách gọi vuex của dự án. (f4a) <br />
----- ✅ Life cycle của dự án vue. (f5a) <br />
----- ✅ Luồng giao thức của vuex trong vue (f6a) <br />
----- ⬜ Custom và sử dụng các thư viện bên ngoài. (f7a) <br />
✅ Cách hoạt động folder bên trong vue masso. (Yêu cầu có video chi tiết nói về cấu trúc và cách hoạt động - đã có). <br />
----- ✅ Sử dụng một git repo dể ví dụ đơn giản về cấu trúc và cách hoạt động của mục "f3a" <br />
----- ✅ Sử dụng một git repo dể ví dụ đơn giản về cấu trúc và cách hoạt động của mục "f4a" <br />
----- ✅ Sử dụng một git repo dể ví dụ đơn giản về cấu trúc và cách hoạt động của mục "f6a" <br />
----- ✅ Sử dụng một git repo dể ví dụ đơn giản về cấu trúc và cách hoạt động của mục "f7a" <br />
✅ Các vấn đề thường gặp phải trong dự án masso khi sử dụng vue. <br />
----- ✅ Khi sử dụng .env, bắt đầu clone dự án. <br />
----- ✅ Khi call api và xử lý lỗi nếu có từ server hoặc chính do client. <br />
----- ✅ Các màn hình báo lỗi thường xuyên xảy ra trong dự án masso. <br />
----- ✅ Tại sao lại không mà lý thuyết lại là có. <br />

#### 😂 Node documentation 
⬜ Tìm hiểu về nodejs <br />
⬜ Các kiến thức nền cấn biết trước khi thực hiện dự án. <br />
----- ⬜ Xử lý API như thế nào. <br />
----- ⬜ Tại sao lại REST API trong các dự án của masso. <br />
----- ⬜ Các xây dựng API FOLDER đơn giản (thực hành một ví dụ nhỏ liên quan tới CRUD. <br />
----- ⬜ TÌm hiểu về Mongo DB. <br />
---------- ⬜ Mongo DB là gì, cách kết nối và các giải pháp cơ bản giữa các phương thức kết nối. <br />
---------- ⬜ Sử dụng models mongo sao cho phù hợp trong các dự án. <br />
---------- ⬜ Cách tư duy nhanh để tạo các model có thể sử dụng lại trong dự án masso :D <br />
----- ⬜ Áp dụng mongodb vào một rest api nhỏ. (thực hiện một CRUD) <br />
⬜ Cấu trúc folder của một dự án nodejs rest api phù hợp. <br />
------ ⬜ GIải thích luồng hoạt động của các folder trong dự án. <br />
------ ⬜ Sử dụng các folder phát triển tiếp thế nào nếu cần bổ sung thêm. <br />
------ ⬜ Hướng cải thiện folder nếu sau này có nhu cầu. <br />
⬜ GIải thích luồng hoạt động của toàn bộ dự án masso/zinbee <br />
------ ⬜ Sử dụng kỹ thuật gì để phát triển hệ thống. <br />
------ ⬜ Các vấn đề gặp phải trong dự án và những giải pháp đang có. <br />
⬜ Vẫn tiếp tục xây dựng thêm.... <br />

## Quy định về thay đổi nội dụng documentation (Contributing)

Chúng tôi muốn bạn đóng góp cho nội dung của chúng tôi và làm cho documentation thậm chí còn tốt hơn ngày hôm nay! Dưới đây là các nguyên tắc chúng tôi muốn bạn tuân theo:

### Quy tắc ứng xử

Hãy giúp chúng tôi giữ nội dung mở và hữu ích. Xin vui lòng đọc và làm theo quy định của chúng tôi [Quy tắc ứng xử](CODE_OF_CONDUCT.md)

### Questions, Bugs, Features

#### Có câu hỏi hoặc vấn đề?

Không mở các vấn đề cho các câu hỏi hỗ trợ chung vì chúng tôi muốn giữ các vấn đề GitHub cho các báo cáo lỗi và yêu cầu tính năng. Bạn đã có nhiều cơ hội tốt hơn để trả lời câu hỏi của mình trên các nền tảng hỗ trợ chuyên dụng, tốt nhất là [Stack Overflow](https://stackoverfollow.com).

Stack Overflow là một nơi tốt hơn để đặt câu hỏi vì:

- Có hàng ngàn người sẵn sàng giúp đỡ về Stack Overflow.
- Câu hỏi và câu trả lời luôn sẵn sàng để xem công khai cho câu hỏi / câu trả lời của bạn.
- Hệ thống bỏ phiếu của Stack Overflow đảm bảo rằng các câu trả lời tốt nhất có thể nhìn thấy rõ.

Để tiết kiệm thời gian của bạn và chúng tôi, chúng tôi sẽ đóng một cách có hệ thống tất cả các vấn đề là yêu cầu hỗ trợ chung và chuyển hướng mọi người đến phần bạn đang đọc ngay bây giờ.

Các kênh hỗ trợ như: 

- [Nhóm thảo luận của Masso](https://google.com)
- [Quản lý công việc](https://google.com)

#### Tìm thấy một vấn đề hoặc lỗi?

Nếu bạn tìm thấy một lỗi trong mã nguồn, bạn có thể giúp chúng tôi bằng cách gửi một vấn đề đến Kho lưu trữ GitHub của chúng tôi. Thậm chí tốt hơn, bạn có thể gửi Yêu cầu kéo với một sửa chữa.

Vui lòng đọc tại [Quy định báo cáo](#submit) bên dưới.

#### Muốn thay đổi nội dung documentation?

Nếu bạn có một gợi ý cho tài liệu, bạn có thể mở một vấn đề và phác thảo vấn đề hoặc cải thiện mà bạn có - tuy nhiên, tự mình tạo tài liệu sửa lỗi sẽ tốt hơn nhiều!

Nếu bạn muốn giúp cải thiện các tài liệu, bạn nên cho người khác biết những gì bạn đang làm để giảm thiểu nỗ lực trùng lặp. Tạo một vấn đề mới (hoặc nhận xét về một vấn đề hiện có liên quan) để cho người khác biết bạn đang làm gì.

Nếu bạn đang thực hiện một thay đổi nhỏ (lỗi đánh máy, phrasing), đừng lo lắng về việc gửi vấn đề trước. Sử dụng nút "Cải thiện tài liệu này" màu xanh lam thân thiện ở phía trên bên phải của trang tài liệu để phân bổ kho lưu trữ tại chỗ và thực hiện thay đổi nhanh chóng. Thông điệp cam kết được định dạng sẵn với đúng loại và phạm vi, vì vậy bạn chỉ phải thêm mô tả.

Đối với các bản sửa lỗi lớn, vui lòng xây dựng và kiểm tra tài liệu trước khi gửi PR để chắc chắn rằng bạn đã vô tình đưa ra bất kỳ vấn đề về bố cục hoặc định dạng nào. Bạn cũng nên đảm bảo rằng thông điệp cam kết của bạn tuân theo [Commit Message Guidelines](#commit-message)

### Vấn đề với quy định báo cáo

Trước khi bạn gửi vấn đề tìm kiếm kho lưu trữ, có thể câu hỏi của bạn đã được trả lời.

Nếu sự cố của bạn có vẻ là một lỗi và chưa được báo cáo, hãy mở một vấn đề mới. Giúp chúng tôi tối đa hóa nỗ lực chúng tôi có thể dành để khắc phục sự cố và thêm các tính năng mới, bằng cách không báo cáo các sự cố trùng lặp.

Biểu mẫu "vấn đề mới" chứa một số lời nhắc mà bạn nên điền vào để dễ hiểu và phân loại vấn đề hơn.

Nói chung, việc cung cấp các thông tin sau sẽ tăng khả năng vấn đề của bạn được xử lý nhanh chóng:

- **Tổng quan về Sự cố** - nêu lỗi được đưa ra, viết một cách ngắn gọn xúc tích.
- **Lý do tìm ra được sự cố** - Giải thích tại sao bạn tìm ra được bug này.
- **Vấn đề liên quan** - có một vấn đề tương tự đã được báo cáo trước đây?
- **Gợi ý cách khắc phục** - nếu bạn không thể tự sửa lỗi, có lẽ bạn có thể chỉ ra những gì có thể gây ra sự cố (dòng mã hoặc cam kết)

Dưới đây là một ví dụ tuyệt vời về một vấn đề được xác định rõ: https://github.com/masso/README.md/issues/5069.

Nếu bạn nhận được sự giúp đỡ, hãy giúp đỡ người khác. Good karma rulez!

### Hướng dẫn Pull Request Submission

Trước khi bạn gửi yêu cầu `pull`, hãy xem xét các nguyên tắc sau:

- Tìm kiếm [GitHub](https://github.com) cho một Yêu cầu `pull`. Nếu bạn không muốn nhân đôi.
- Tạo theo dạng development.
- Thực hiện thay đổi của bạn ở một nhánh mới:
```sh
git checkout -b my-fix-branch master
```
- Tạo bản chỉnh sửa của bạn, bao gồm các trường hợp ví dụ.
- Tuân thủ theo [Coding Rules](https://google.com)
- Nếu các thay đổi ảnh hưởng đến API công khai, hãy thay đổi hoặc thêm tài liệu liên quan.
- Run `yarn lint --fix` để kiểm tra xem bạn đã tuân theo các quy tắc mã hóa được thi hành tự động chưa.
- Sự thay đổi commit của bạn hãy sử dụng theo quy định commit.
```sh
git commit -a
```
Chú ý: tùy chọn dòng lệnh commit `-a` tùy chọn sẽ tự động "add" và "rm" các tệp đã chỉnh sửa.
- Đẩy nhánh của bạn lên github
```sh
git push origin my-fix-branch
```
- Nếu bạn thấy rằng tích hợp Travis đã thất bại, hãy xem nhật ký trên Travis để tìm hiểu xem các thay đổi của bạn có gây ra lỗi thử nghiệm hay không, thông báo cam kết không đúng, v.v. một thành viên trong nhóm để bản dựng có thể được khởi động lại.
- Nếu chúng tôi đề xuất thay đổi, thì:
    + Thực hiện các cập nhật cần thiết.
    + Commit sự thay đổi tới nhánh của bạn (e.g. `my-fix-branch`)
    + Đẩy các thay đổi vào kho lưu trữ GitHub của bạn (Nó sẽ được cập nhật tại Pull Request).
    
    Bạn cũng có thể sửa đổi cáccommit ban đầu và buộc `push` chúng đến nhánh của bạn.
    ```sh
    git rebase master -i
    git push origin my-fix-branch -f
    ```
    Điều này thường dễ thực hiện hơn, nhưng các cam kết riêng biệt rất hữu ích nếu Yêu cầu kéo có chứa các lần lặp có thể thú vị để xem cạnh nhau.

Cảm ơn sự đóng góp của bạn!

#### Sau khi pull request được merged

Sau khi pull request của bạn được hợp nhất, bạn có thể xóa chi nhánh của mình một cách an toàn và kéo các thay đổi từ kho lưu trữ chính (ngược dòng):

- Xóa nhánh remote trên Github thông qua GitHub web UI hoặc local như bên dưới

```sh
git push origin --delete my-fix-branch
```
- Chuyển qua nhánh master
```sh
git checkout master -f
```
- Xóa nhánh dưới local
```sh
git branch -D my-fix-branch
```
- Cập nhật nội dụng mới nhất thông qua upstream.
```sh
git pull --ff upstream master
```
