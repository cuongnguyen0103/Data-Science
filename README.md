# Data-Science
## tải và xóafile lên github
### Dung lượng nhỏ
- Có thể tải trực tiếp từ github
- Tải bằng ứng dụng 'Github Destop'
### Dung lượng lớn
- Nên nén thành file gzip để bới dung lương
- import gzip
- import pickle
### xóa
- Khi xóa bạn nên xóa file trên thư mục cần tạo ra khi cài xong github Destop
- rồi mở github Destop
#### lưu
- with gzip.open('surprise.pkl.gz', 'wb') as f:
    - pickle.dump(algorithm, f)
#### đọc
- with gzip.open('surprise.pkl.gz', 'rb') as f:
  - <Tên biến> = pickle.load(f)
- Sau đó tải lên bình thường (cái này nên dùng vì Github cho dung lượng có hạn, bị hết cần phải mua)
- Nếu không được:
  + Tải git-lfs (hoặc Git: vì mình tải Git trước up ko được nên mình cài thêm git-lfs)
  + Đứng tại thư mục chúng ta bặt bược tạo khi cài 'Github Destop' để đây lên Github
  + mở cmd gõ các lệnh:
      + git lfs install
      + git lfs track "*.pkl"  #Tùy loại file: (zip/pkl/csv/..)
       + git add .gitattributes
       + git lfs migrate import --include="*.pkl"
       + git add "surprise.pkl" (đây là tên file cần thêm, nếu nhiều file thì dùng nhiều lệnh)
       + git commit -m "initial commit"
       + git push origin main
## Lỗi pickle.load(file)
- nếu bạn bị lỗi này có nghĩa là thư viện của file .pkl chưa được cài như 'surprise', 'gensim', 'underthesea'
- khi mình tải file lên github không chạy được mình thử dùng cách này
- Khi bạn tạo file 'requirements.txt' tại thư mục với các nội dung tương tự streamlit
  + numpy
  + pandas
  + matplotlib
  + seaborn
  + scikit-learn
  + scikit-surprise
  + surprise
  + gensim
  + underthesea
  - tại cmd chứa 'requirements.txt' bạn gõ lệnh: pip install -r requirements.txt
  - sau đó bạn kiểm tra xem (mình thì xóa file trên github và tải file này lên lại)
## Nếu gặp lỗi RROR: Failed building wheel for gensim hoặc RROR: Failed building wheel for numpy
- nên chỉnh phiên bản file 'requirements.txt' trên github mình sửa 2 mục như sau:
  + numpy==1.21.5
  + gensim==4.3.3

### Đôi khi mình phải xóa app và tạo mới mới thành công
# CHÚC MỌI NGƯỜI THÀNH CÔNG
  
