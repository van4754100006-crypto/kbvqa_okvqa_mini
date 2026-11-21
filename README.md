# kbvqa_okvqa_mini

Code thực nghiệm cho tiểu luận "Bài toán trả lời câu hỏi về ảnh dựa trên tri thức ngoài (KB-VQA): tổng quan và phân tích phương pháp Wiki-PRF" (học phần Nhập môn Xử lý ngôn ngữ tự nhiên, Trường Đại học Quy Nhơn).

## Nội dung
So sánh hai cấu hình trên 200 mẫu đầu của tập val OK-VQA:
- **Không RAG:** Qwen2.5-VL-3B-Instruct trả lời trực tiếp từ ảnh và câu hỏi.
- **Có RAG đơn giản:** nêu thực thể chính trong ảnh, tìm 5 bài Wikipedia qua API, xếp hạng lại bằng all-MiniLM-L6-v2, giữ 2 đoạn đưa vào prompt (ý tưởng Processing – Retrieval – Filtering của Wiki-PRF).

Chỉ suy luận, không huấn luyện thêm.

## Kết quả (độ chính xác %)
| Độ đo | Không RAG | Có RAG |
|---|---|---|
| Chuẩn (khớp chính xác) | 55,0 | 50,0 |
| Nới lỏng (khớp một phần) | 61,5 | 58,8 |

Trong 200 mẫu, RAG tốt hơn 13 mẫu, kém hơn 23 mẫu, không đổi 164 mẫu. Chênh lệch chưa có ý nghĩa thống kê (kiểm định dấu, p ≈ 0,13). Đây là thực nghiệm minh họa, không so trực tiếp với số liệu của bài báo gốc.
