---
layout: post
title:  "[Series SCSS] #1 What is SASS/SCSS?"
author: sal
categories: [ Scss, sass ]
image: assets/images/2019/9/scss.png
featured: true
---

Làm việc với CSS là việc thường xuyên của mọi thể loại dev :v. Có khi nào bạn thấy chán cách viết CSS ‘chay’ mà bạn vẫn đang viết thường ngày? Có cách nào để viết CSS một cách chuyên nghiệp hơn không ? Có đấy, cùng tìm hiểu trong bài viết này nhé.

###  SASS là gì?

*Sass* là một ngôn ngữ bản định kiểu dược biên dịch thành css. Nó cho phép sừ dụng các biến, quy tắc lồng nhau, mixin, hàm và nhiều hơn thế nữa, tất cả đều có cú pháp tương thích hoàn toàn với css. SASS giúp giữ các bảng định kiểu lớn được tổ chức tốt và giúp dễ dàng chia sẻ thiết kế trong và trên các dự án.

### SCSS là gì

*Sass* được thiết kế bởi các lập trình viên Ruby. Bởi vậy, Sass stylesheet sử dụng cú pháp giống như Ruby với việc có các dấu ngoặc {}, dấu chấm phấy. Nó khác với cách viết css truyền thống nên viết code Sass khá khó hiểu. 

Nhắm thư hẹp khoảng cách giữa Sass và Css thì sự có mặt của Scss là sự nâng cấp với cú pháp thân thiện hơn, viết dễ dàng hơn, dễ hiều hơn.

Giờ thử mình thử viết Scss như thế nào nha!

### Quy tắc Nested Rule (Quy tắc xếp chồng)

Ví dụ mình có một đoạn HTML 

```
<div class="container">
    <div class="row">
        <div class="navbar col-12">
            <a class="brand">Dk</a>
            <ul class="nav">
                <li><a href="#">Nav 1</a></li>
                <li><a href="#">Nav 2</a></li>
            </ul>
        </div>
    </div>
</div>
```

Giờ bạn muốn css cho thẻ nav, li, a thì Css thuần bạn sẽ viết như sau: 

```
.navbar ul.nav {
    list-style: none;
}
```

Tiếp đến

```
.navbar ul.nav li {
    padding: 5px;
}
```

Bạn sẽ tiếp tục vòng lặp đó đến khi hết các thẻ cần css, như vật thật tốn công phải không khi có cấu trúc html phức tạp.

Nested Rule của SASS sinh ra để giúp bạn làm điều trên một cách đơn giản hơn.

```
.navbar {
    ul.nav {
        list-style: none;
 
        li {
            padding: 5px;
 
            a {
                text-decoration: none;
            }
        }
    }
}
```

Đoạn code trên sau khi được compile ra thì sẽ như sau: 

```
.navbar ul.menu {
    list-style: none;
}
.navbar ul.menu li {
    padding: 5px;
}
.navbar ul.menu li a {
    text-decoration: none;
}
```

Và trong thực tế quy tắc xếp chồng được sử dụng rất nhiều khi vào các dự án có viết css bằng Scss/Sass.

### Kết luận

Trên đây mình đã giới thiệu bạn thế nào là SASS/SCSS. Trong các bài viết tiếp theo mình sẽ hướng dẫn các bạn dùng biến, mixin, extend, import trong Scss nha. 
