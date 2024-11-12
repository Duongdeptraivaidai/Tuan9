#### Bai 1 buoi 1: (Tìm lỗi) Chương trình sau có lỗi gì? Ghi lại câu thông báo lỗi này, sửa lỗi và cho
biết kết quả xuất ra màn hình, ý nghĩa của chương trình? Ba tham số trong hàm có gì
khác nhau? Ý nghĩa của sự khác biệt này?
```c
#include<iostream>
using namespace std;

void abc(int x, int k, int& k) {
	kq= 1;
	for (int i = 1; i <= k; i++) kq *= x;
}
int main() {
	int a = 2, b = 3, c;
	abc(a, b, c);
	cout << c;
	return 0;
}
```
#### Bai 2 buoi 1: (Xuất chữ) Viết hàm xuất chữ khi truyền vào số từ 1 - 9. Nhập sai thì không xuất.
```c
#include <iostream>
using namespace std;

void Xuatchu(int n);
void Xuatchu(int n) {
	
		switch (n) {
		case 1:cout << "Mot "; break;
		case 2:cout << "Hai "; break;
		case 3:cout << "Ba "; break;
		case 4:cout << "Bon "; break;
		case 5:cout << "Nam "; break;
		case 6:cout << "Sau "; break;
		case 7:cout << "Bay "; break;
		case 8:cout << "Tam "; break;
		case 9:cout << "Chin "; break;
		}
	
}
int main() {
	int n;
	cout << "Nhap vao mot so nguyen tu 1-9: ";
	cin >> n;
	 Xuatchu(n);
	 return 0;
}
```
#### Bai 3 buoi 1:  (Hoán vị hai số) Viết chương trình cho phép người dùng nhập vào hai số thực (số
thứ nhất lưu vào biến first và số thứ hai lưu vào biến second) và sau đó gọi hàm HoanVi
(swap) với các tham số thực là first và second. Hàm HoanVi (swap) có các tham số hình
thức là number1 và number2 sẽ hoán vị giá trị của hai biến. Các giá trị sau khi hoán vị sẽ
được xuất trong hàm main
Ví dụ:
Hay nhap so thu nhat, sau do enter: 80
Hay nhap so thu hai, sau do enter: 70
Ban nhap cac so la 80 va 70.
Sau khi hoan vi, so thu nhat co gia tri 70.
So thu hai co gia tri la 80.

```c
#include<iostream>
using namespace std;

void hoanvi(float a, float b) {
	swap(a, b);
	cout << "\n So thu nhat sau hoan vi la: " << a;
	cout << "\n So thu hai sau khi hoan vi la: " << b;
}
int main() {
	float a, b;
	cout << "Hay nhap vao so thu nhat, sau do Enter: ";
	cin >> a;
	cout << "Hay nhap vao so thu hai, sau do Enter: ";
	cin >> b;
	cout << "Ban nhap vao cac so la " << a << " va " << b;

	hoanvi(a, b);
	return 0;

}
```
#### Bai 4 buoi 1: (Tính tốc độ Km/h) Viết chương trình nhập vào số Km và số giờ đã đi du lịch.
Chương trình xác định số tốc độ Km trên một giờ. Việc tính toán này được thực hiện
trong một hàm khác hàm main, hàm main sẽ xuất lên kết quả tính toán. Hàm tính toán
123
Nhập Xuất
2 hai
7 bay
10sẽ có ba tham số: Km, Hours và KmPerHour. Tham số nào được truyền tham trị và
truyền tham chiếu? Kết quả xuất lên màn hình lấy chính xác đến hai số thập phân.
Ví dụ:
Hay nhap so km da di du lich:
475
Hay nhap so gio da di du lich:
8
Toc do cua ban la 59.38 km tren gio
```c
#include <iostream>
#include <iomanip>
using namespace std;
void KperH(float K, float H, float& KpH);
void KperH(float K, float H, float& KpH) {
	KpH = K / H;
}
int main() {
	int H, K;
	float KpH;
	cout << "hay nhap vao so km da di du lich: "; cin >> K;
	cout << "hay nhap vao so gio da di du lich: "; cin >> H;
	cout << fixed << setprecision(2);
	KperH(K,H,KpH);
	cout << "Toc do cua ban la " << KpH << " km tren gio";
	return 0;
}
```
#### Bai 5 buoi 1: (Chuyển điểm số sang điểm chữ) Viết chương trình cho phép người dùng nhập
vào số lượng điểm số. Sau đó, chương trình cho người dùng nhập vào từng điểm số.
Chương trình sẽ tính tổng của các điểm được nhập và truyền nó cùng với số lượng điểm
tới một hàm có một tham số “truyền tham chiếu”. Hàm này sẽ tính điểm trung bình các
điểm được nhập. Hàm main sẽ xác định điểm chữ tương ứng với điểm trung bình trên
theo quy đổi:
90 – 100 A
80 – 89 B
70 – 79 C
60 – 69 D
0 – 59 F
Ví dụ:
Hay nhap so luong diem so:
3
Hay nhap diem so thu 1 (0 – 100):
90
Hay nhap diem so thu 2 (0 – 100):
80
Hay nhap diem so thu 3 (0 – 100):
50
Diem chu tuong ung la: C
```c
#include <iostream>
using namespace std;

void tinhdiem(int soluong, int& tong) {
	for (int i = 1; i <= soluong; i++) {
		int diem;
		cout << "Hay nhap vao so luong diem so thu " << i << " (0-100): ";
		cin >> diem;
		tong += diem;
	}
	tong /= soluong;
}
int main() {
	int soluong, tong = 0;
	cout << "hay nhap vao so luong diem so: "; cin >> soluong;
	tinhdiem(soluong, tong);
	cout << "Diem chu tuong ung la: ";
	if (tong >= 0 && tong <= 60)cout << "F";
	else if(tong <70)cout << "D";
	else if (tong < 80)cout << "C";
	else if (tong < 90)cout << "B";
	else if (tong < 100)cout << "A";
	return 0;
}
```
#### Bai 6 buoi 1:(Tính số giây đồng hồ) Viết một hàm tính số giây theo giờ (gồm ba thông tin giờ,
phút và giây) tính từ thời điểm cuối cùng của đồng hồ theo cấu trúc 24h. Sử dụng hàm
này để tính khoảng cách theo giây giữa hai giờ cho trước, cả hai giờ đều nằm trong chu
kỳ 24h đồng hồ. Hàm được mô tả như sau:
//********************************************************
124// Ten ham: Seconds(int, int, int, int &)
// Tac vu: Ham nay tinh tong so giay
// Dau vao: hours, minutes, seconds
// Dau ra: TotalSeconds (thay doi tham so thuc tuong ung)
//********************************************************
```c

```
#### Bai 7 buoi 1: (Tính cạnh huyền) Định nghĩa một hàm có tên Hypotenuse để tính chiều dài cạnh
huyền của một tam giác vuông khi biết chiều dài hai cạnh còn lại. Hàm này được mô tả
như sau:
//********************************************************
// Ten ham: Hypotenuse(double, double, double &)
// Tac vu: Ham nay tinh va xuat ra chieu dai canh huyen
// Dau vao: Side1 va Side2
// Dau ra: Hypotenuse (thay doi tham so thuc tuong ung)
//********************************************************
```c
#include <iostream>
#include <cmath>
using namespace std;

void Hypotenuse(double a, double b, double& c) {
	c = sqrt(pow(a, 2) + pow(b, 2));
	cout << "Do dai canh huyen la: " << c;
}

int main() {
	double a, b, c;
	cout << "Nhap vao do dai hai canh goc vuong: ";
	cout << "canh thu 1: "; cin >> a;
	cout << "canh thu 2:"; cin >> b;
	Hypotenuse(a, b, c);
	return 0;

}
```
#### Bai 8 buoi 1:(Xuất bảng cửu chương) Viết hàm xuất bảng cửu chương thứ k. Nhập vào số n>1,
gọi hàm trên để xuất các bảng cửu chương từ 2 đến n.
Ví dụ:
Hay nhap so n (n > 1): 3
Bảng cửu chương 2:
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
2 x 6 = 12
2 x 7 = 14
2 x 8 = 16
2 x 9 = 18
2 x 10 = 20
Bảng cửu chương 3:
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30
```c
#include<iostream>
using namespace std;

void bangcuuchuong(int n) {
	for (int i = 1; i <= n; i++) {
		cout << "bang cuu chuong " << i << " \n";
		for (int j = 1; j <= 10; j++) {
			int nhan = i * j;
			cout << i << " x " << j << " = " << nhan << endl;
		}
	}
}

int main() {
	int n;
	cin >> n;
	if (n <= 1) {
		cout << "Vui long nhap n (n>1): ";
		return true;
	}
	bangcuuchuong(n);
	return 0;
}
```
