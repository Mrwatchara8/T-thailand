# RandomWebsiteStar
Star me if you want to star https://github.com/swrdfgd/RandomWebsite since I keep delete this repo and create it again
ข้ามไปที่เนื้อหา
เมนูนําทาง
มีนน่า
ไทยแอลเอ็มคัท

พิมพ์เพื่อค้นหา /
รหัส
ปัญหา
1
คําขอดึงข้อมูล
การดําเนินการ
โครงการ
ความปลอดภัย
ข้อมูล เชิง ลึก
อวาตาร์เจ้าของ
ไทยแอลเอ็มคัท
สาธารณะ
meanna/ไทย LMCUT
ไปที่ไฟล์
t
Name		
ผู้แต่ง
สุทีรา
อัปเดต readme
กอท.ฮล. 37C1202
 · 
3 years ago
ข้อมูล
อัปโหลดตัวอย่างชุดข้อมูล
3 years ago
graphic_lmcut
เพิ่มรูปตัวอย่างใหม่
3 years ago
แอลเอ็มคัท
เพิ่ม GitKeep
3 years ago
รถไฟ
เพิ่มโมเดลสําหรับภาษาอังกฤษ
3 years ago
.gitignore
ปรับปรุงรหัส LM
5 years ago
ใบอนุญาต
สร้างใบอนุญาต
5 years ago
README.md
อัปเดต readme
3 years ago
setup.py
รหัสรี팩คเตอร์
3 years ago
การนําทางไฟล์ที่เก็บ
อ่านให้มี
ใบอนุญาต MIT
ThaiLMCut - Word Tokenizer สําหรับภาษาไทย โดยพื้นฐานการเรียนรู้แบบโอนย้ายและสองทิศทาง-LSTM
ThaiLMCut - Word Tokenizer สําหรับภาษาไทย โดยพื้นฐานการเรียนรู้แบบโอนย้ายและสองทิศทาง-LSTM
ประมาณ
อัพเดต
ความต้องการ
ติดตั้ง LMCut เป็นแพ็คเกจ
วิธีใช้ LMCut
ฝึกโมเดลภาษา
ฝึกโทเค็นใหม่
เครดิต
กิตติคุณ
ผู้ร่วมให้ข้อมูล
ใบอนุญาต
ประมาณ
โทเค็นใช้การเรียนรู้การถ่ายโอนจากโมเดลภาษาตัวละครซึ่งได้รับการฝึกฝนในคลังข้อมูลรีวิวโรงแรมขนาดใหญ่ของไทยและ InterBEST2009
อัพเดต: ตอนนี้ tokenizer รองรับทั้งข้อความภาษาไทยและภาษาอังกฤษ
ลอง ThaiLMCut ใน Colab
บทความ: ThaiLMCut: Unsupervised Pretraining for Thai Word Segmentation
บิบเท็กซ์


ตัวอย่างข้อมูลจากรีวิวโรงแรม


อัพเดต
(พฤษภาคม 2565) เพิ่มโมเดลที่รองรับทั้งภาษาไทยและภาษาอังกฤษ
(พฤษภาคม 2022) ปรับปรุง README และโค้ด
ความต้องการ
หลาม 3.5+
ไฟทอร์จ 1.0+
มึนงง
ติดตั้ง LMCut เป็นแพ็คเกจ
ดาวน์โหลดไฟล์น้ําหนักจาก:
โมเดลโทเค็นไนเซอร์
tokenizer ที่รองรับภาษาไทยและภาษาอังกฤษ
https://drive.google.com/drive/folders/1rUs765_FzalZWOJRSRL0cbQGW3lrV4JM?usp=sharing
tokenizer ที่รองรับเฉพาะภาษาไทย
https://drive.google.com/drive/folders/1hJ4jsXdypP4mqZDsEgxEEfO-CLwAzHTj?usp=sharing
ย้ายไฟล์น้ําหนักไปยังไดเร็กทอรีนี้:
lmcut/weight/
สร้างวงล้อแพ็คเกจโดยใช้:
python setup.py bdist_wheel

ติดตั้งแพ็คเกจโดยใช้:
pip install dist/lmcut*
วิธีใช้ LMCut
Tokenize ข้อความภาษาไทยที่กําหนด
from lmcut import tokenize
text = "โรงแรมดี สวยงามน่าอยู่มากๆ"
result = tokenize(text)
print(result)
ผลลัพธ์คือรายการของโทเค็น:

['โรง', 'แรม', 'ดี', 'สวยงาม', 'น่า', 'อยู่', 'มาก', 'ๆ']
ฝึกโมเดลภาษา
เตรียมชุดข้อมูลสําหรับการฝึกอบรม
ในการฝึกโมเดลภาษา คุณควรจัดเตรียมไฟล์ข้อความดิบสองไฟล์.txt หนึ่งสําหรับการฝึกอบรมและอีกหนึ่งเพื่อการพัฒนา โมเดลนี้รองรับเฉพาะข้อความภาษาไทยและภาษาอังกฤษเท่านั้น อักขระจากภาษาอื่นจะถือว่าเป็นอักขระที่ไม่รู้จัก
ดูตัวอย่างใน data/lm_data/
คุณสามารถกําหนดชุดข้อมูลแบบกําหนดเองของคุณในฟังก์ชันใน .get_path_data_LMtrain/get_corpus.py
ชื่อชุดข้อมูลที่กําหนดไว้ที่นั่นจะใช้ในแฟล็กบรรทัดคําสั่ง--dataset
หมายเหตุ: หากคุณใช้ InterBEST2009 เครื่องหมายขอบเขตจะต้องถูกลบออกก่อน
เมื่อต้องการฝึกโมเดลภาษาใหม่ ให้เรียกใช้
python train/LanguageModel.py \
--dataset [dataset name] \
--batchSize 60 \
--char_dropout_prob 0.01 \
--char_embedding_size 200 \
--hidden_dim 500 \
--layer_num 3 \
--learning_rate 0.0001 \
--sequence_length 100 \
--epoch 10 \
--len_lines_per_chunk 1000 \
--optim [adam or sgd] \
--lstm_num_direction [2 means bidirectional and 1 means uni directional] \
--add_note "..add some note.."
ตัวอย่างคําสั่ง

python train/LanguageModel.py \
--dataset default \
--batchSize 32 \
--char_dropout_prob 0.01 \
--char_embedding_size 100 \
--hidden_dim 100 \
--layer_num 2 \
--learning_rate 0.0001 \
--sequence_length 100 \
--epoch 3 \
--len_lines_per_chunk 100 \
--optim adam \
--lstm_num_direction 2 \
--add_note "test if code runs properly"
หากต้องการฝึกโมเดลภาษาต่อ ให้เรียกใช้

python train/LanguageModel.py \
--load_from [model name to resume] \
--dataset [dataset name] \
--epoch 3 \
--learning_rate 0.0001 \
--over_write 1
[language model name] ต้องขึ้นต้นด้วย ตัวอย่างเช่น .LMLM_2022-05-03_18.59.59

สิ่งประดิษฐ์ของโมเดลอยู่ใน train/checkpoints_LM

หลังการฝึกอบรม จะมีการสร้างไฟล์ 4 ไฟล์
LM_2022-05-03_18.28.05          (log file)
LM_2022-05-03_18.28.05.json     (data about model structure used when reloading the model)
LM_2022-05-03_18.28.05.pth.tar  (model weights)
LM_log.csv    (a log file in csv, for collecting experiment results)
โมเดลภาษาที่ผ่านการฝึกอบรมล่วงหน้า
โมเดลภาษาที่ได้รับการฝึกอบรมจากข้อมูลรีวิวโรงแรม (คําศัพท์: ไทยและอังกฤษ)
https://drive.google.com/drive/folders/1QKOctAPYIpC7b3beLGvOJ-h43-T85Yjy?usp=sharing
คําสั่ง (หมายเหตุ: ชุดข้อมูล TY ไม่พร้อมใช้งานต่อสาธารณะ)

python train/LanguageModel.py \
--dataset ty \
--batchSize 64 \
--char_dropout_prob 0.01 \
--char_embedding_size 200 \
--clip_grad 0.5 \
--hidden_dim 514 \
--layer_num 2 \
--learning_rate 0.0001 \
--sequence_length 150 \
--epoch 20 \
--len_lines_per_chunk 1000 \
--optim adam \
--lstm_num_direction 2 \
--lr_decay 0.01 \
--sgd_momentum 0.02
ฝึกโทเค็นใหม่
อินพุตที่คาดหวังคือชุดข้อมูล InterBEST2009 หรือคลังข้อมูลใด ๆ ที่มีเครื่องหมายขอบเขต|
คุณสามารถแยก InterBEST2009 โดยใช้ .create_dataset.py
ดูเป็นตัวอย่างdata/toy
กําหนดเส้นทางชุดข้อมูลการฝึกอบรม พัฒนา และทดสอบในฟังก์ชันใน get_path_data_tokenizertrain/get_corpus.py
ในการฝึกโทเค็นใหม่ คุณสามารถเรียกใช้:

python train/Tokenizer.py \
--dataset default \
--epoch 3 \
--lstm_num_direction 2 \
--batchSize 30 \
--sequence_length 80 \
--char_embedding_size 100 \
--hidden_dim 60 \
--layer_num 2 \
--optim adam \
--learning_rate 0.0001
ในการโหลดโมเดลภาษาที่ผ่านการฝึกอบรมล่วงหน้า (เลเยอร์การฝังและเลเยอร์ที่เกิดซ้ํา) ไปยังโทเค็นไนเซอร์และฝึกอบรม

python train/Tokenizer.py \
--load_from [language model name] \
--dataset default \
--epoch 2 \
--learning_rate 0.0001 \
--over_write 0
[language model name] ควรขึ้นต้นด้วย ตัวอย่างเช่น .LMLM_2022-05-03_18.59.59
หากต้องการกลับมาฝึกอบรมโทเค็นไนเซอร์ต่อ คุณสามารถเรียกใช้

python train/Tokenizer.py \
--load_from [tokenizer name] \
--dataset default \
--epoch 2 \
--learning_rate 0.0001 \
--over_write 1
[tokenizer name] should begin with , for example, .TokenizerTokenizer_2022-05-03_20.46.35

Use if you want to replace the loaded model with the trained model.--over_write 1

With it will save the trained model as a separate model.--over_write 0

Model artifacts are in train/checkpoints_tokenizer

After the training, 4 files will be generated.
Tokenizer_2022-05-03_18.53.26          (log file)
Tokenizer_2022-05-03_18.53.26.json     (data about model structure used when reloading the model)
Tokenizer_2022-05-03_18.53.26.pth.tar  (model weights)
tokenizer_result.csv    (a log file in csv, for collecting experiment results)
For more detail about other arguments, see and train/Tokenizer.pytrain/LanguageModel.py

data/news_00001.txt and are from InterBEST2009 corpus by NECTECdata/TEST_100K.txt

Credits
Most of the code are from Tabula nearly rasa: Probing the Linguistic Knowledge of Character-Level Neural Language Models Trained on Unsegmented Text
Some codes are from DeepCut and Attacut
Acknowledgements
The project is funded by TrustYou. The author would like to sincerely thank TrustYou and other contributors.

Contributors
Suteera Seeha
Ivan Bilan
Liliana Mamani Sanchez
Johannes Huber
Michael Matuschek
License
All original code in this project is licensed under the MIT License. See the included LICENSE file.

ประมาณ
ไม่มีคําอธิบาย เว็บไซต์ หรือหัวข้อให้ไว้
ทรัพยากร
 อ่านให้เห็น
ใบอนุญาต
 ใบอนุญาต MIT
 กิจกรรม
ดาว
 15 ดาว
ผู้เฝ้าดู
 5 กําลังดู
ส้อม
 5 ส้อม
ที่เก็บรายงาน
รุ่น
ไม่มีการเผยแพร่ข่าวประชาสัมพันธ์
แพ คเกจ
ไม่มีแพ็กเกจที่เผยแพร่
ภาษา
หลาม
100.0%
Footer
© 2025 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact
Manage cookies
Do not share my personal information
ผลการค้นหาโค้ด
