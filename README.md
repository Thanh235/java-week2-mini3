# java-week2-mini3
115-1 Java Week2 作業

測試題二：自行選三個 0 至 99 的整數，將輸入和實際輸出記在 README。
int result = 12 + 34 + 56 ;
MOVI R1, 12
MOVI R2, 34
ADD R0, R1, R2
MOVI R2, 56
ADD R0, R0, R2
STORE [0], R0

問題一：第一次 ADD 之後，為什麼能用第三個整數覆蓋 R2？
ans: 前兩個(R1,R2)整數相加的結果已經入暫存器 R0，R2 空出來，拿第三個數字把 R2 覆蓋掉。

問題二：若輸入改成 int result=7+3+1;，目前程式為什麼無法按預期讀取？
ans: 因為Scanner懶切詞 它預設純粹就是靠空白鍵（Space）來分開每個 token 的。
如果沒有留空格，整串黏成 result=7+3+1;，它根本不會知道那是什麼變數，最後進去就一坨，nextInt() 要抓整數時就沒東西吃，或是格式對不上。