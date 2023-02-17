Binary search là một thuật toán tìm kiếm hiệu quả được sử dụng để tìm kiếm phần tử trong một mảng đã được sắp xếp. Thuật toán này đưa ra giả định rằng mảng đã được sắp xếp theo thứ tự tăng dần hoặc giảm dần, và từ đó có thể tìm kiếm nhanh chóng bằng cách chia mảng thành các phần bằng nhau và so sánh giá trị tại giữa mảng với giá trị cần tìm. Nếu giá trị tại giữa mảng nhỏ hơn giá trị cần tìm, thuật toán sẽ tìm kiếm trong mảng con bên phải của giá trị đó, và nếu giá trị tại giữa mảng lớn hơn giá trị cần tìm, thuật toán sẽ tìm kiếm trong mảng con bên trái của giá trị đó. Thuật toán này lặp lại quá trình trên đến khi tìm thấy giá trị cần tìm hoặc không thể tìm thấy giá trị đó trong mảng.

Trong C++, chúng ta có thể sử dụng hàm std::binary_search trong thư viện <algorithm> để thực hiện tìm kiếm nhị phân trên một mảng. Hàm này có cú pháp như sau:

cpp
```cpp
template< class ForwardIt, class T >
bool binary_search( ForwardIt first, ForwardIt last, const T& value );
```
first và last là các iterators (con trỏ) tới phần đầu và phần cuối của mảng cần tìm kiếm.
value là giá trị cần tìm trong mảng.
Hàm trả về true nếu giá trị value có trong mảng, ngược lại trả về false.

Dưới đây là một ví dụ về việc sử dụng hàm std::binary_search để tìm kiếm phần tử trong một mảng đã được sắp xếp:

c++
```cpp
#include <algorithm>
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> nums = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    int value = 5;
    bool found = std::binary_search(nums.begin(), nums.end(), value);

    if (found) {
        std::cout << "Value " << value << " found in the array." << std::endl;
    } else {
        std::cout << "Value " << value << " not found in the array." << std::endl;
    }

    return 0;
}
```
Đầu ra sẽ là:

c
```cpp
Value 5 found in the array.
```
