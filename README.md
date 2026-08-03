-----
安裝：

pip install "qrcode[pil]"

pip install pyzbar

pip install imageio-ffmpeg



-----
1.先將程式資料夾壓成 zip 

2.清除 .net 程式碼以外的東西
python clean_zip.py 你的檔案.zip 乾淨版.zip

3.解析檔案中那一些佔據最多容量
python clean_zip.py analyze 乾淨版.zip

4.依解析內容排除不要的檔案
python clean_zip.py clean 乾淨版.zip 更乾淨版.zip --exclude-ext .png --exclude-ext .gif --exclude-ext .jpg --exclude-ext .png --exclude-ext .ttf

5.將檔案壓成更小
python clean_zip.py repack 刪除不要檔案版.zip 更小版.tar.xz

6.轉換為影片
python zip_to_qr_video.py encode 更小版.tar.xz output.mp4 --chunk-size 1200 --fps 3 --repeat 2




-----
1.還原為壓縮檔
python zip_to_qr_video.py decode PXL.mp4 restored.tar.xz --sample-fps 15

2.解壓縮
tar -xf restored.tar.xz


