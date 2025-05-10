
# 📊 Sentiment Analysis on Financial News

## 📑 Mô tả dự án
Dự án thực hiện phân tích cảm xúc trên tập dữ liệu tin tức tài chính, Bộ dữ liệu này bao gồm các tiêu đề tin tức tài chính kèm theo nhãn cảm xúc tương ứng (Positive, Negative hoặc Neutral). Thông tin trong bộ dữ liệu chủ yếu gồm nội dung tiêu đề và nhãn phân loại cảm xúc, giúp
phục vụ các bài toán phân tích tác động của tin tức đến thị trường tài chính và tâm lý nhà đầu tư. Sử dụng xen kẽ phương pháp rule-based, học máy và học sâu để đưa ra những dự báo về hình thái cảm xúc của tin tức tài chính

## 📌 Quy trình thực hiện

1. **Mount Google Drive**
   - Kết nối Google Colab với Google Drive để đọc file dữ liệu `all-data.csv`.

2. **Import thư viện cần thiết**
   - Các thư viện chính: `pandas`, `numpy`, `nltk`, `matplotlib`, `seaborn`, `plotly`, `colorama`, `wordcloud`, `tqdm`.

3. **Đọc dữ liệu**
   - Đọc file `all-data.csv` chứa các dòng tin tức và nhãn gốc.

4. **Tiền xử lý văn bản**
   - Làm sạch văn bản:
     - Chuyển chữ thường
     - Loại bỏ URL, ký tự đặc biệt, số, dấu câu, emoji
     - Tokenize và stem từ
     - Loại bỏ stopwords

5. **Phân tích cảm xúc bằng Vader**
   - Tính điểm sentiment `compound` cho từng câu
   - Quy đổi thành nhãn:
     - `positive` nếu compound ≥ 0.05
     - `negative` nếu compound ≤ -0.05
     - `neutral` nếu nằm giữa

6. **Thống kê, khai phá dữ liệu, trực quan hóa**
   - **File notebook**: EDA_Sentiment_Analysis_Financial_News.ipynb
   - Đếm số lượng câu theo từng sentiment
   - Vẽ biểu đồ phân phối điểm sentiment
   - Tạo WordCloud cho từng nhóm sentiment

7. **Dự báo cảm xúc bằng mô hình học máy và học sâu**
   - **File notebook**: Sentiment_Analysis_Financial_News.ipynb
   - **Vector hóa văn bản**: Sử dụng TF-IDF, CountVectorizer hoặc Embedding layer.
   - **Xây dựng mô hình học máy**: Logistic Regression, Random Forest, SVM.
   - **Xây dựng mô hình học sâu**: MLP, LSTM, hoặc GRU cho bài toán phân loại sentiment.
   - **Huấn luyện và đánh giá mô hình**: Chia train/test, tính độ chính xác (accuracy), F1-score, confusion matrix.

## 📂 Cấu trúc dữ liệu
- **Input:** `all-data.csv` với các cột:
  - `Label`: sentiment gốc
  - `Message`: câu tin tức
- **Output:** DataFrame với thêm các cột:
  - `Clean_Text`
  - `Vader_Score`
  - `Sentiment`

## 📦 Yêu cầu
- Python 3.x
- Các thư viện: pandas, numpy, nltk, matplotlib, seaborn, plotly, wordcloud, tqdm, colorama

## 🚀 Cách chạy
1. Tải notebook lên Google Colab
2. Mount Google Drive
3. Cài các thư viện cần thiết (nếu chưa có)
4. Chạy lần lượt các cell
