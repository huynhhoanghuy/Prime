# Prime

_Số nguyên tố là số tự nhiên chỉ chia hết cho 1 và chính nó._

Qua nhiều thống kê số học, thấy rằng nếu một số tự nhiên thỏa mãn một số tính chất nào đó của số nguyên tố (chẳng hạn như Fermat nhỏ) thì có nhiều khả năng nó là số nguyên tố. Từ đó, khái niệm **số nguyên tố xác suất** xuất hiện:

- Số tự nhiên n thỏa mãn tính chất nào đó của số nguyên tố được gọi là số nguyên tố với một xác suất nào đó.

- Số vừa là nguyên tố xác suất vừa là **hợp số** còn gọi là **số giả nguyên tố**.

Tùy theo tính chất mà nó thỏa mãn, ta sẽ có các loại số giả nguyên tố khác nhau: số giả nguyên tố Fermat, số giả nguyên tố Euler, số giả nguyên tố Euler-Jacobi.

=> Số nguyên tố xác suất vẫn có khả năng là số nguyên tố.

=> Số giả nguyên tố hoàn toàn không phải là số nguyên tố mà là hợp số.

Note: Số nguyên tố nhiều hơn số giả nguyên tố. Khi một số thỏa mãn định lý Fermat, thì khả năng số đó là số nguyên tố cao hơn là số giả nguyên tố.

# Bài toán kiểm tra tính nguyên tố

Bài toán: Kiểm tra một số có phải là số nguyên tố hay không?

Mục đích: Trở nên quan trọng khi các hệ mật mã khóa công khai ra đời.

# Bài toán kiểm tra số giả nguyên tố

Bài toán: Kiểm tra một số có phải là số _giả_ nguyên tố hay không?

Mục đích: Số các hợp số thỏa mãn quan hệ "là hệ quả của prime" rất ít => Dùng nó để tạo nên các số nguyên tố xác suất



Note: An integer x that is a Fermat pseudoprime to all values of a that are coprime to x is called a Carmichael number.

# Một số ý tưởng cơ bản:

Cách 1: Duyệt từ 2 đến n-1. (O(n))

Cách 2: Duyệt từ 2 đến n-1 theo bước nhảy 2 (chỉ xét số lẻ): 2x+1. (O($n\over2$))

Cách 3: Duyệt từ 2 đến $\sqrt{n}$. (O($\sqrt{n}$))

Cách 4: Duyệt từ 2 đến $\sqrt{n}$ theo bước nhảy 2 (chỉ xét số lẻ): 2x+1. (O($\sqrt{n}\over2$))

Cách 5: Nhận thấy tất cả số tự nhiên đều được tạo từ 6k, 6k +1, 6k + 2, 6k + 3, 6k + 4, 6k + 5.

_Dễ thấy 6k, 6k+2, 6k + 4 chia hết cho 2; 6k, 6k +3 chia hết cho 3_

=>_ Nếu số n không chia hết cho 2 và 3_, tức là n sẽ có dạng 6k + 1 hoặc 6k + 5.

Mặt khác, 6k + 5 = 6(k+1) -1 = 6K -1.

=> n sẽ có dạng 6k $\pm$ 1. Như vậy chúng ta sẽ giảm được phần lớn không gian tìm kiếm.

Tóm lại, ta cần duyệt các số có dạng 6k - 1 và (6k -1) + 2 tối đa $\sqrt{n}$ phần tử => Start từ flag = 5, mỗi vòng lặp xét điều kiện flag và flag + 2, sau đó tăng flag += 6.
(O($\sqrt{n}\over6$))
