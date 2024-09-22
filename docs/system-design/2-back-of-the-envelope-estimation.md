# Back of the envelope estimation

- Giả sử số lượng user sử dụng hệ thống là không quá nhiều ban đầu. Chúng ta thiết kế hệ thống 1 mức đơn giản nhất và thêm thắt các optimization sau đó để hướng tới mục tiêu hệ thống có thể hỗ trợ hơn `10tr user`.
- 1 thời điểm có khoảng `10k user đang online`.
- Mỗi user sẽ follow trung bình bởi `200` người.
- 1 vài user đặc biệt sẽ được follow bởi 100k user.
- Tạo bài post: `10tr` user, `3tr` user
  - user 10 post/day => 30M/day => `350 QPS, max QPS: 1500QPS`.
- Xem newsfeed:
  - `5` tiếng, `200` post ~ `10` request => `30M/h` => `8.3k QPS, max QPS: 40k QPS.`
