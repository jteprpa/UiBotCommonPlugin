# UiBotCommonPlugin

Uibot 內建函數可能不足，此Plugin 提供可能需要的功能

安裝方式：將 /Release/ 底下所有檔案複製到 RPA專案\extend\DotNet

使用方式：

1 查詢檔案建立日期
DateTime = UiBotCommonPlugin.GetFileCreationTime(string path)



2 查詢檔案最後更新日期
DateTime = UiBotCommonPlugin.GetFileLastWriteTime(string path)


3 寄HTML格式的信件
UiBotCommonPlugin.SmtpSendHtmlMail(string Host, int Port, string Account, string Password, string Subject, string Body, string From, string To, string Cc, string Bcc, string file)

Host 寄信IP
Port 寄信Port
Account 寄信帳號
Password 寄信密碼
Subject 信件主旨
Body 信件內容
Form 寄信者
To 收信者
CC 副本收信者
Bcc 密件副本收信者
file 附加檔案

範例:

	UiBotCommonPlugin.SmtpSendHtmlMail("mailserver.com",587,"account","password","RPA test", "test123","sean@everbiz.com.tw","sean@everbiz.com.tw;test@everbiz.com.tw","","","D:\\1.pdf")
	


4 把PDF 拆開，每頁一個檔案
UiBotCommonPlugin.PdfExtractPages(string sourcePDFpath, string outputPDFpath, int startpage, int endpage)

5 把PDF轉成Excel
UiBotCommonPlugin.PdfToXls(string source, string xlspath)

6 根據文字在PDF內的座標整理出來正確順序的文字內容
UiBotCommonPlugin.TextFromPage(string _filePath, int startPage, int endPage)

7 調整圖片大小
UiBotCommonPlugin.ThumbnailImage(string filepath, int width, int height)

8 UrlEncode utf8
UiBotCommonPlugin.UrlEncode(string data)

9 二階陣列轉Excel
UiBotCommonPlugin.ArrayToExcel(string[][] data, string target)

10 簡體轉繁體
UiBotCommonPlugin.ConvertToTraditional(string data)

11 Excel 所有工作表
arrayRet = JSON.Parse(UiBotCommonPlugin.ExcelGetSheetsName("D:\\2203252139.xls"))

12 Excel 讀取區域內容轉成陣列
arrayRet = JSON.Parse(UiBotCommonPlugin.ExcelReadRange("D:\\2203252139.xls","Sheet1","C5:G9"))

13 Excel 讀取所有內容轉成陣列
arrayRet = JSON.Parse(UiBotCommonPlugin.ExcelReadToArray("D:\\2203252139.xls","Sheet1"))

14 Excel 讀取欄位數量
intRet = UiBotCommonPlugin.ExcelGetColumsCount("D:\\2203252139.xls","Sheet1")

15 Excel 讀取筆數
arrayRet = UiBotCommonPlugin.ExcelGetRowsCount("D:\\2203252139.xls","Sheet1")

16 Excel 讀取某筆內容轉成陣列
arrayRet = JSON.Parse(UiBotCommonPlugin.ExcelReadRow("D:\\2203252139.xls","Sheet1",0))
