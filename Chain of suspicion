import sys
from PySide2.QtWidgets import *
from PySide2.QtGui import *
from ui_COS import Ui_COS

class cos(QMainWindow, Ui_COS):
    def __init__(self):
        super().__init__()
        self.setupUi(self)
        # 按钮信号
        self.pbtn_DF.clicked.connect(self.template_1)
        self.pbtn_XD.clicked.connect(self.template_2)
        self.pbtn_save.clicked.connect(self.save)
        self.pbtn_ok.clicked.connect(self.Optional)
        # self.pbtn_submit.clicked.connect(self.verify)
        self.show()
    def template_1(self):
        try:
            global list_cos
            for_num = int(self.le_num.text())
            if for_num > 2:
                a = '2.你不知道我认为你'
                list_cos = ["1.你不知道我是善意还是恶意", "2.你不知道我认为你是善意还是恶意"]
                for i in range(for_num - 2):
                    a = a.split(".")
                    if int(a[0]) % 2 == 0:
                        b = "认为我"
                    else:
                        b = "认为你"
                    a = str(i+3) + "." + a[-1] + b
                    list_cos.append(a + "是善意还是恶意")
                self.le_ok.setText(",".join(list_cos))
                try:
                    self.le_X.setText(list_cos[int(self.le_xc.text())-1])
                except:
                    QMessageBox.information(self,"猜疑链生成器","请输入整数,且不能超过要生成的项数")
            else:
                QMessageBox.information(self,"猜疑链生成器","请输入整数(要大于2)")
        except:
            QMessageBox.information(self,"猜疑链生成器","请输入整数(要大于2)")
    def template_2(self):
        try:
            global list_cos
            for_num = int(self.le_num.text())
            if for_num > 2:
                a = '2.你不知道我怎么想你'
                list_cos = ["1.你不知道我怎么想你", "2.你不知道我怎么想你怎么想我"]
                for i in range(for_num - 2):
                    a = a.split(".")
                    if int(a[0]) % 2 == 0:
                        b = "怎么想我"
                    else:
                        b = "怎么想你"
                    a = str(i+3) + "." + a[-1] + b
                    list_cos.append(a)
                self.le_ok.setText(",".join(list_cos))
                try:
                    self.le_X.setText(list_cos[int(self.le_xc.text())-1])
                except:
                    QMessageBox.information(self,"猜疑链生成器","请输入整数,且不能超过要生成的项数")
            else:
                QMessageBox.information(self,"猜疑链生成器","请输入整数(要大于2)")
        except:
            QMessageBox.information(self,"猜疑链生成器","请输入整数(要大于2)")
    def Optional(self):
        content_1,content_2,content_3,content_4,content_5 = self.le_1.text(),self.le_2.text(),self.le_3.text(),self.le_4.text(),self.le_5.text()
        # 1325,132415,13241425,1324142415
        try:
            global list_cos
            for_num = int(self.le_num.text())
            if for_num > 2:
                a = "2." + str(content_1) + str(content_3) + str(content_2) + str(content_4) + str(content_1)
                list_cos = ["1." + str(content_1) + str(content_3) + str(content_2) + str(content_5), "2." + str(content_1) + str(content_3) + str(content_2) + str(content_4) + str(content_1) + str(content_5)]
                for i in range(for_num - 2):
                    a = a.split(".")
                    if int(a[0]) % 2 == 0:
                        b = str(content_4) + str(content_2)
                    else:
                        b = str(content_4) + str(content_1)
                    a = str(i+3) + "." + a[-1] + b
                    list_cos.append(a + str(content_5))
                self.le_ok.setText(",".join(list_cos))
                try:
                    self.le_X.setText(list_cos[int(self.le_xc.text())-1])
                except:
                    QMessageBox.information(self,"猜疑链生成器","请输入整数,且不能超过要生成的项数")
            else:
                QMessageBox.information(self,"猜疑链生成器","请输入整数(要大于2)")
        except:
            QMessageBox.information(self,"猜疑链生成器","请正确填写!")
    def save(self):
        if len(list_cos) != 2:
            try:
                with open("处理结果.txt", "w") as f:
                    f.write("处理结果: " + ",".join(list_cos) + "\n选择项数: " + list_cos[int(self.le_xc.text())-1])
            except:
                QMessageBox.information(self,"猜疑链生成器","请先制作好再保存哦~")
        else:
            QMessageBox.information(self,"猜疑链生成器","请先制作好再保存哦~")
if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = cos()
    sys.exit(app.exec_())
