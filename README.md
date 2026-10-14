# BÀI TẬP LÀM THÊM NHÓM 2
## 1. Nội dung báo cáo
- Dùng lệnh Get-ChildItem -Filter "*.log" -Recurse để đọc tất cả các file kể cả file con có trong folder
- Dùng Get-content | Select-String "ERROR" dể lọc các flie có chứa 'ERROR' 
- Sau khi tìm được tất cả các file có 'ERROR' ta tạo 1 flie báo cáo "bao_cao_loi.txt" và gom tất cả các file 'ERROR' vào trong
* Các bước: 
- 'Get-ChildItem -Filter "*.log" -Recurse' => tìm kiếm tất cả các flie mở rộng và quét sâu vào trong folder
- 'ForEach-Object {Get-content  $_.FullName | Select-String "ERROR" }' lấy file log ở bước trên để xử lí vòng lặp và đọc nội dung trong file hiện tại 
- 'Select-Object -ExpandProperty Line' lọc và bóc tách nội dung chứa văn bản(line) của các dòng lỗi vừa tìm được
- 'Out-File -FilePath "bao_cao_loi.txt" -Append' ghi tất cả kết quả thu được vào file 'bao_cao_loi.txt'
- CODE: Get-ChildItem -Filter "*.log" -Recurse | Get-content | Select-String "ERROR" | Select-Object -ExpandProperty Line | Out-File -FilePath "bao_cao_loi.txt" -Append# BTTEST
# BTTEST
