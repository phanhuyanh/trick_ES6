# trick_ES6

### trick 1
```
Có thể gán 1 biến vào giá trị 1 hàm

f = parameters => x = 1;

Khi gọi hàm f() thì biến x cũng được gán bằng 1
```


### trick 2
17. **Bitwise Not (~) in JS**
    * Đảo ngược tất cả các bit của number. Vd: 1010 --> 0101
    * Trong JS, số lưu trữ dạng dấu phẩy động 64bit(float 64bit), nhưng tất cả các thao tác toán tử bit đều thực hiện trên số nghị phân 32bit. Trước khi thực hiện bit , JS sẽ convert sang số nguyên có dấu 32 bit. Sau khi thực hiện xong, JS lại convert lại về số 64 bit
    * VD: 
         1. 00000000000000000000000000000101 (5)
         2. 11111111111111111111111111111010 (~5 = -6)
    * Dấu của số đó chính là dấu bit ngoài cùng. 1 là âm và 0 là dương
    * Trick: đơn giản ta chỉ cần hiểu khi sử dụng toán tử (~) là : ```~a = -(a + 1)```
   
18. **Bitwise Right shift(>>)**
    * Syntax: n >> a
    * Dịch a bit sang bên phải và giữ nguyên dấu của n
    
19. **Bitwise Left shift(<<)**
    * Syntax: n << a
    * Dịch a bit sang bên trái và thêm vào bên phải các bit 0

29. **Bitwise (Zero Fill) Right shift(>>>)**
    * Syntax: n >>> a
    * Dịch a bit sang bên phải và thêm vào sau bên trái các bit 0

### trick 3
   * Expresstion: exp1 = exp2 = exp3
   * Thực hiện từ trái sang phải như sau: gán exp1 = exp2 và exp2 = exp3. Nếu trong exp1 có biểu thức thì tính luôn
   * VD: s[v -= v / 2] = i -= s[v]
   * Giải thích: 
       * Gán giá trị phần tử s[v -= v / 2] = i nhưng đồng thời v -= v / 2
       * Giá trị của i -= s[v] mà lúc này giá trị của v đã là v -= v/2
   * Có thể viết lại như sau:
   ```
   v -= v/2;
   i -= s[v]
   s[v] = i
   ```
