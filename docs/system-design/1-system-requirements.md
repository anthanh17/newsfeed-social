# System requirement

Design a `Newsfeed` for social network like Facebook

- Newsfeed là trang chủ khi ta đăng nhập 1 mạng xã hội như Fb, X, etc ... bao gồm tất cả những post của những người bạn, page or group của mình đang theo dõi và được `sort` theo recommend và time.

- `Design 1 mạng xã hội đơn giản` gồm người dùng và những bài post của họ. Các người dùng có thể theo dõi nhau và có 1 trang newfeeds để xem những thay đổi đó.

# Requirement clarifications

- Chỉ có người dùng và những người dùng follow nhau giống như 1 đồ thị có hướng (không có page, group ...)
- Thông tin của 1 Post gồm: người đăng, thời gian đăng, nội dung gồm (text, img) và nhưng like/comment mà 1 người nói về nó
- Thông tin 1 người dùng gồm: tên, username, password (đã mã hoá) và list người đang follow, được follow.
- Ứng dụng hỗ trợ:
  - Tạo account và login.
  - Người dùng được follow/unfollow người khác.
  - Người dùng được quyền sửa thông tin cá nhân như tên, password.
  - Tạo bài đăng.
  - Newfeed: Xem những feed của những người mình follow.
  - Xem trang chủ của 1 user (bao gồm các feed và thông tin cơ bản).
  - Tương tác với 1 post: comment và like comment đấy.
