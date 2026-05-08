# Node.js Portable Setup (Giải pháp cho máy giới hạn quyền Admin)

## Tổng quan
Dự án này được cấu hình để chạy **Node.js** và **npm** trực tiếp từ thư mục nội bộ. Giải pháp này cực kỳ hữu ích khi bạn làm việc trên môi trường Windows bị giới hạn quyền Administrator (không thể cài đặt phần mềm vào `C:\Program Files`, không thể sửa biến môi trường hệ thống, và không thể chạy `nvm use` theo cách thông thường).

## Tải
```bash
nvm install 22.10.0
nvm use 22.10.0
```

## Cấu trúc thư mục dự án
Để mọi thứ hoạt động linh hoạt, dự án cần được tổ chức như sau:

```text
my-project/
├── nvm/                   <-- Thư mục chứa môi trường Node
│   ├── nvm.exe            <-- File thực thi nvm-noinstall
│   └── v22.10.0/          <-- Folder Node.js
│       ├── node.exe       <-- File chạy chính của Node
│       └── ...
├── .vscode/
│   └── settings.json      <-- Cấu hình tự động hóa môi trường
├── src/                   <-- Mã nguồn dự án
└── package.json