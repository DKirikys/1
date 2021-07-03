import os
import xlwt

print("Введите путь")
n = input()
content = os.listdir(n)
workbook = xlwt.Workbook()
ws = workbook.add_sheet('sheet')
workbook.save('file.xls')
count = 0
i = 0
for v in content:
    if "~$" in v:
        continue
    else:
        count += 1
        ws.write(i, 0, count)
        ws.write(i, 1, v)
        i += 1
workbook.save('file.xls')
