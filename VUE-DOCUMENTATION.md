# Kiến thức cơ bản về Vue.js

Khi nói về các Javascript framework, chúng ta thường cho rằng các framework cần cung cấp mọi thứ ta cần để xây dựng một SPA (Single Page Application) hoàn thiện (gọi là Full framework). Tuy nhiên, một framework được thiết kế theo cách đó thường tự mua vào mình sự nặng nề, và bất kỳ sự hiểu biết hay kinh nghiệm cụ thể về các framework đó không mang lại hữu ích khi ta xây dựng bên ngoài kịch bản SPA. Các framework này cũng cung cấp quá mức cần thiết trong các trường hợp sự dụng tương đối đơn giản của chúng ta. Lan man một hồi vậy thì Progressive Framework là cái méo gì nhỉ?

Progressive framework là khái niệm khá mới, có thể hiểu thay vì như Full-featured framework hay Monolithic framework cung cấp tất cả mọi thứ cần có để xây dựng app trong một framework duy nhất, thì progresive framework lại chia thành các thành phần nhỏ khác nhau, và ta có thể dần dần lựa chọn các thành phần tham gia vào sao cho phù hợp. Vue.js là một trong số các progressive framework. Phần lõi của Vue.js tập chung chủ yếu vào phần View. Chúng ta có thể sử dụng mỗi lõi của Vue để tạo view hoặc CÓ THỂ cài THÊM các thành phần như vuex để quản lý state trong app hay vue-router cho SPA routing... hoặc là không dùng thêm.

Phần lõi có thể hoạt động tốt một mình và có thể chạy mượt mà khi ghép thêm các thành khác lại với nhau. Đó cũng chính là một trong những đặc điểm của progressive framework. Bởi phạm vi bài viết hôm nay tập trung vào Vue nên các khái niệm như Progressive framework, Full-featured framework hay Monolithic framework thì có lẽ tôi phải hẹn riêng một bài khác để nói riêng về chúng. Bạn cũng có thể tham khảo thêm về Progressive framework tại đây.

> Chúng ta cần học kiến thức để thực hiện các dự án một cách nhanh chóng, đồng nghĩa với việc trong documentation sẽ giúp bạn nằm bắt các vùng kiến thức cơ bản nhất để thực hiện dự án. Điều này không đông nghĩa với việc bạn sẽ học như vậy, nếu bạn muốn đi một cách vững chắc, hãy học một cách nghiêm túc. Mình có chia sẻ chi tiết tại cuối phần docs này nếu bạn quan tâm nó.

## Các kiến thức quan trọng nhất trong vue.js để thực hiện dự án.

Thực ra để nói một cách khách quan bạn cần gì thì mình không thể trả lời được, nhưng trong trường hợp này, với việc thực hiện các dự án ở công ty MASSO thì mình sẽ bổ sung những phần kiến thức mình cho là bạn cần phải được biết đầu tiên.

+ Xử lý components
+ Cách code scss theo quy tắc BEM
+ Cách sử dụng axios để giao thức với API
+ Cách gọi vuex của dự án.
+ Life-cycle của dự án vue.
+ Luồng giao thức của vuex trong vue.
+ Custom và sử dụng các thư viện (nếu có)