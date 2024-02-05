# Day 3:

## **Variables**

1 MB = 1,024 Kilobytes

Biến là vị trí lưu trữ dữ liệu được đặt tên trong bộ nhớ máy tính. Bằng cách sử dụng tên biến trong chương trình. Trên thực tế chúng ta đang đề cập đến dữ liệu
được lưu trữ ở đó

### Cách đặt tên biến:
![Untitled](https://github.com/Merisreal/C-language-Note/assets/139641711/d7bc5874-16f5-46c1-92d8-ded725cfe6d9)

Note:
Lowercase letters → variable names (tên biến)

All-uppercase letters → constants (hằng)

Đối với nhiều trình biên dịch, tên biến C có thể dài tới 31 ký tự. (Thật ra nó có thể dài hơn thế, nhưng trình biên dịch chỉ xem xét 31 ký tự đầu tiên của tên )

Có 2 quy ước đặt tên biến

- interest_rate
- InterestRate

→ Nên chọn 1 quy ước 

## Numeric Variable Types (biến số)

C có rất nhiều loại biến số → nên chọn loại phù hợp để ít tốn tài nguyên máy tính

EX: 

- Intergers values (1,199,-9) sử dụng ít bộ nhớ hơn
- Floating-point values (123,00000) sử dụng nhiều bộ nhớ hơn
![2](https://github.com/Merisreal/C-language-Note/assets/139641711/643071b4-f03e-4bea-89db-2684d222615a)


```c
//See size of type
printf( “\nA char is %d bytes”, sizeof( char ));
printf( “\nAn int is %d bytes”, sizeof( int ));
.......

```

![12](https://github.com/Merisreal/C-language-Note/assets/139641711/e4ad2080-5da5-4c4f-883f-674b27be4e44)

Note:

- The size of a char is one byte.
- The size of a short is less or equal to the size of an int.
- The size of an int is less or equal to the size of a long.
- The size of an unsigned is equal to the size of an int.
- The size of a float is less or equal to the size of a double

![1231](https://github.com/Merisreal/C-language-Note/assets/139641711/65910ebe-472e-4484-a215-c49ad762a794)

## **Variable Declaration (**Khai báo Biến)

```c
int count, number, start;
float percent, total;
```

**Initializing Variables (Khởi tạo giá trị cho biến)**

```c
int count; /* Set aside storage space for count */
count = 0; /* Store 0 in count *

```

Khi khai báo biến, trình biên dịch đã tạo ra không gian lưu trữ riêng cho biến đó. Tuy nhiên giá trị ban đầu khởi tạo đó không được xác định. Nó có thể là 0 hay một số ngẫu nhiên 

Nếu gán giá trị cho biến vượt quá phạm vi. Chương trình sẽ thông báo lỗi: 

```c
int weight = 100000;
unsigned int value = -2500
```

### The typedef Keyword:

The typedef keyword is used to **create a new name for an existing data type**. 

Tạo một tên mới cho kiểu dữ liệu đã tồn tại

```jsx

typedef int TestInterger;
```

Tạo ra TestInterger đồng nghĩa với int. Sau đó, bạn có thể sử dụng TestInterger để xác định các biến kiểu int, như trong ví dụ này:

```jsx

TestInterger count;
```

Note:

Typedef không tạo ra một kiểu dữ liệu mới, nó chỉ là thay tên đổi họ cho kiểu dữ liệu đã tồn tại :V

## Constants (Hằng)

Giống với biến, hằng cũng được lưu trữ bởi chương trình, nhưng gái trị của hằng sẽ không bị thay đổi trong suốt chương trình. C có 2 laoị hằng:

- Literal Constants
- Symbolic Constants

### **Literal Constants (chả biết dịch tv sao, chắc là Hằng)**

Trong một số tài liệu nó còn được gọi là Immediate value (hằng số tức thời) → nó được thể hiện là giá trị đại diện cho chính nó

EX:

```c
int count = 20;
float tax_rate = 0.28;
```

20 & 0.28 là **Literal Constants.** 2 giá trị này được clâu trong 2 biến là count và tax_rate

### **Symbolic Constants (Hằng số ký hiệu)**

Nó được thể hiện bởi name(symbol) trong chườn trình. Nó cũng ko thay đổi gái trị  

Khi cần tới giá trị của hằng trong chương trình, hãy dùng tên của nó như sử dụng tên biến. Gía trị của hằng số ký hiệu chỉ cần nhập 1 lần duy nhất, ở phần đầu 

Ưu điểm hơn so với Literal Constants

EX: Tính chu vi hình tròn

```c
Circumference = 3.14 * (2*radius)
Area = 3.14 * (radius**) * (**radius**)**
```

Thay vì thế → Sử dụng **Symbolic Constants** ta sẽ có đoạn code clean hơn → Gán Pi với 3.14

```c
Circumference = Pi* (2*radius)
Area = Pi* (radius) * (radius)
```

→ Nếu ta muốn thay đổi giá trị của Pi từ 3.14 → 3.14159 ta cũng có thể dễ dàng thay đổi tại nơi khai báo đầu tiên của hằng

### Defining Symbolic Constants

Có 2 phương pháp định nghĩa hằng trong C

```c
#define CONSTNAME literal
const int count = 100
```

**Với #define**

- Không cần ‘;’ cuối câu
- Có thể đặt bất kỳ đâu trong đoạn code → Thông thường đặt trước khi bắt đầu main()

```c
#define PI 3.14159
#define PIPETTE 100
```

**Với const**

```c
const int count = 100;
const long debt = 12000000, float tax_rate = 0.21;
```

Trong một dòng lệnh, const sẽ tác động hết (EX2)

Sự khác biệt giữa #define và const là pointers và variable scope (con trỏ và phạm vi biến đổi )

Code EX:

```c
#include <stdio.h>

#define GAM_PER_KG  1000

const int TARGET_YEAR = 2024;

int main()
{
    float kg;
    int nam_sinh;

    printf("nhap nam sinh " );
    scanf("%d",&nam_sinh );
    printf("nhap kg ");
    scanf("%f", &kg);

    printf("Tuoi nam 2024 = %d", (TARGET_YEAR - nam_sinh));
    printf("\nSo gam = %2.fg", (GAM_PER_KG * kg));

}
```

# Day 11 Implementing Structures, Unions, and TypeDefs

Structures là một tập hợp gồm một hoặc nhiều biến được nhóm lại dưới một tên duy nhất để dễ dàng thao tác. Các biến trong một cấu Structures, không giống như các biến trong một mảng, có thể có các kiểu dữ liệu khác nhau. Một cấu trúc có thể chứa bất kỳ kiểu dữ liệu nào của C, bao gồm mảng và các cấu trúc khác. Mỗi biến trong một cấu trúc được gọi là thành viên (member) của cấu trúc. Phần tiếp theo hiển thị một ví dụ đơn giản

**Defining and Declaring Structures**

```c
struct coord
{
int x;
int y;
}
```

```c
struct coord {
int x;
int y;
} first, second;
```

Cách 1: Các câu lệnh này xác định kiểu cấu trúc coord và khai báo hai cấu trúc, first & second, thuộc kiểu coord. first & second,là từng trường hợp của kiểu coord; first chứa hai phần tử số nguyên có tên x và y, và second cũng vậy.

```c
struct coord {
	int x;
	int y;
}
/*code... */
struct coord first, second;
```

Cách 2: Phương pháp khai báo cấu trúc này kết hợp việc khai báo với định nghĩa. Phương pháp thứ hai là khai báo các biến cấu trúc ở một vị trí khác trong mã nguồn. 

### **Accessing Members of a Structure**

Các thành viên cấu trúc riêng lẻ có thể được sử dụng như các biến khác cùng loại. 

```c
first.x = 50;
first.y = 100;

//display second
printf("%d,%d, second.x, second.y")
```

Ưu điểm của struct với các biến riêng lẻ:

EX

```c
first = second ;
//can write 
first.x = second.x;
first.y = second.y;
```

⇒ Đối với bài toán phức tạp ⇒ dùng cách này tiết kiệm thời gian 

⇒ Không chỉ vậy, nó còn hữu ích khi thông tin của các kiểu biến khác nhau nên được gộp thành 1 nhóm: địa chỉ nhà, tên,…

```c
#include <stdio.h>

// Define a structure named 'coord' to represent coordinates
struct coord {
    int x;
    int y;
};

int main(void) {
    // Create an instance of the 'coord' structure named 'myPoint'
    struct coord myPoint;

    // Set values for the coordinates
    myPoint.x = 12;
    myPoint.y = 14;

    // Display the coordinates
    printf("\nThe coordinates are: (%d, %d).\n", myPoint.x, myPoint.y);

    return 0;
}
```

```c
The coordinates are: (12, 14)
```

### The struct Keyword

dùng Khai báo Structures (tập hợp 1 hoặc nhiều biến (structure_members) gộp lại dưới 1 cái tên để dễ thao tác)

Structures also can hold arrays, pointers, and other struc-

tures

### **Structures Within Other Structures**

```c
#include <stdio.h>

// Define a structure named 'coord' to represent coordinates
struct coord {
    int x;
    int y;
};

// Define a structure named 'rectangle' to represent a rectangle
struct rectangle {
    struct coord topleft;
    struct coord bottomrt;
};

int main(void) {
    // Create an instance of the 'rectangle' structure named 'mybox'
    struct rectangle mybox;

    // Input the coordinates for the top-left and bottom-right corners
    printf("\nEnter the top-left x coordinate: ");
    scanf("%d", &mybox.topleft.x);

    printf("Enter the top-left y coordinate: ");
    scanf("%d", &mybox.topleft.y);

    printf("Enter the bottom-right x coordinate: ");
    scanf("%d", &mybox.bottomrt.x);

    printf("Enter the bottom-right y coordinate: ");
    scanf("%d", &mybox.bottomrt.y);

    // Calculate the length and width of the rectangle
    int width = mybox.bottomrt.x - mybox.topleft.x;
    int length = mybox.bottomrt.y - mybox.topleft.y;

    // Calculate and display the area of the rectangle
    long area = (long)width * length;
    printf("\nThe area is %ld units.\n", area);

    return 0;
}
```

Red code: Struct của rectangle chứa 2 structures của coord. topleft & bottomrt

Câu lệnh trước chỉ định nghĩa kiểu cấu trúc hình chữ nhật. Để khai báo một cấu trúc,

```c
struct rectangle mybox;
```

<img width="556" alt="ds" src="https://github.com/Merisreal/C-language-Note/assets/139641711/28dc77b5-6d29-4992-b901-2f7aec097518">

### **Structures That Contain Arrays**

```c
struct data
{
int x[4];
char y[10];
};

struct data record;
```
<img width="512" alt="sad" src="https://github.com/Merisreal/C-language-Note/assets/139641711/dc5efb85-4759-4355-9007-bf4474c0bbe9">


**Arrays of Structures**

```c
#include <stdio.h>

// Define a structure to hold entries
struct entry {
    char fname[20];
    char lname[20];
    char phone[10];
};

int main(void) {
    // Declare an array of structures
    struct entry list[4];

    // Loop to input data for four people
    for (int i = 0; i < 4; i++) {
        printf("\nEnter first name: ");
        scanf("%s", list[i].fname);

        printf("Enter last name: ");
        scanf("%s", list[i].lname);

        printf("Enter phone in 123-4567 format: ");
        scanf("%s", list[i].phone);
    }

    // Print two blank lines
    printf("\n\n");

    // Loop to display data
    for (int i = 0; i < 4; i++) {
        printf("Name: %s %s", list[i].fname, list[i].lname);
        printf("\t\tPhone: %s\n", list[i].phone);
    }

    return 0;
}
```

## **Initializing Structures**

simple: 

```c
#include <stdio.h>

// Định nghĩa cấu trúc sale
struct sale {
    char customer[20];
    char item[20];
    float amount;
};

int main(void) {
    // Khởi tạo biến mysale thuộc kiểu cấu trúc sale và gán giá trị ban đầu
    struct sale mysale = {
        .customer = "Acme Industries",
        .item = "Left-handed widget",
        .amount = 1000.00
    };

    // In thông tin từ biến mysale
    printf("Customer: %s\n", mysale.customer);
    printf("Item: %s\n", mysale.item);
    printf("Amount: %.2f\n", mysale.amount);

    return 0;
}
```

```c
#include <stdio.h>

// Định nghĩa cấu trúc customer
struct customer {
    char firm[20];
    char contact[25];
};

// Định nghĩa cấu trúc sale
struct sale {
    struct customer buyer;
    char item[20];
    float amount;
};

int main(void) {
    // Khởi tạo mảng y1990 thuộc kiểu cấu trúc sale và gán giá trị ban đầu
    struct sale y1990[100] = {
        { {"Acme Industries", "George Adams"}, "Left-handed widget", 1000.00 },
        { {"Wilson & Co.", "Ed Wilson"}, "Type 12 gizmo", 290.00 }
        // Các phần tử khác có thể được thêm vào đây theo cùng một cấu trúc
    };

    // In thông tin từ mảng y1990
    for (int i = 0; i < 2; i++) {
        printf("Sale %d:\n", i + 1);
        printf("Firm: %s\n", y1990[i].buyer.firm);
        printf("Contact: %s\n", y1990[i].buyer.contact);
        printf("Item: %s\n", y1990[i].item);
        printf("Amount: %.2f\n", y1990[i].amount);
        printf("\n");
    }

    return 0;
}
```

Explain:

This is what occurs in this code:

1. The structure member y1990[0].buyer.firm is initialized to the string “Acme Industries” (line 14).

2. The structure member y1990[0].buyer.contact is initialized to the string “George Adams” (line 14).

3. The structure member y1990[0].item is initialized to the string “Left-handed widget” (line 15).

4. The structure member y1990[0].amount is initialized to the amount 1000.00 (line 16).

## **Structures and Pointers**

```c
struct data
{
int *value;
int *rate;
} first;
```

Tuy nhiên cần phải gắn địa chỉ cho biến 

```c
first.value = &cost;
first.rate = &interest;
```
<img width="489" alt="sa" src="https://github.com/Merisreal/C-language-Note/assets/139641711/cb041001-2e73-485c-b4e9-cd8083d1e7e9">


Lí do sử dụng pointer thay cho sử dụng array kiểu char ⇒ **Storing**

```c
struct msg
{
char p1[10];
char p2[10];
} myptrs;
...
strcpy(p1, “Minneapolis”); /* Wrong! String longer than array.*/
strcpy(p2, “MN”); /* Okay, but wastes space because */
/* string shorter than array. */
```

Nếu bạn xác định một cấu trúc chứa các con trỏ để gõ char thì những hạn chế trên sẽ ko có. Mỗi phiên bản của cấu trúc chỉ chứa không gian lưu trữ cho con trỏ. C

### **Creating Pointers to Structures**

```c
struct part
{
short number;
char name[10];
};

//code here
...

struct part *p_part;
//can 1 address cho con tro
struct part gizmo;

p_part = &gizmo
```

<img width="519" alt="dsa" src="https://github.com/Merisreal/C-language-Note/assets/139641711/8e2e2b22-436a-4cbb-91e6-e638cbcc7a0a">

```c
(*p_part).number = 100;
```

p_part phải được đặt trong ngoặc đơn vì toán tử thành viên (member operator) ‘.’ có độ ưu tiên cao hơn toán tử gián tiếp ()

### Sử dụng →

Ký hiệu này được đặt giữa tên con trỏ và tên thành viên. Ví dụ, để truy cập number member của gizmo bằng con trỏ p_part :

```c

p_part -> number
```

Nhìn vào một ví dụ khác, nếu str là một cấu trúc, p_str là một con trỏ tới str và memb là thành viên của str, bạn có thể truy cập str.memb bằng cách viết

```c
p_str -> memb
```

<img width="519" alt="dsad" src="https://github.com/Merisreal/C-language-Note/assets/139641711/80cec93e-c967-441f-a5bb-ebb7a285a6e6">

### **Pointers and Arrays of Structures**

```c
struct part
{
short number;
char name[10];
}

struct part data[100];

//initialize pointer to array

struct part *p_part;
p_part = &data[0];

//or can write

p_part = data;

printf(“%d %s”, p_part->number, p_part->name);
```

### **Passing Structures as Arguments to Functions**

```c
#include <stdio.h>

struct data {
    float amount;
    char fname[30];
    char lname[30];
} rec;

void print_rec(struct data displayRec);

int main(void) {
    /* Input the data from the keyboard. */
    printf("Enter the donor's first and last names,\n");
    printf("separated by a space: ");
    scanf("%s %s", rec.fname, rec.lname);

    printf("\nEnter the donation amount: ");
    scanf("%f", &rec.amount);

    /* Call the display function. */
    print_rec(rec);

    return 0;
}

void print_rec(struct data displayRec) {
    printf("\nDonor %s %s gave $%.2f.\n", displayRec.fname,
           displayRec.lname, displayRec.amount);
}
```

<img width="372" alt="ca" src="https://github.com/Merisreal/C-language-Note/assets/139641711/183a635c-c3d6-4c1e-8ca6-0db78a842951">

# Day 9 & 15 Pointer - basic to medium

Trước tiên phải hiểu về kiến thức cơ bản về các máy tính chứa thông tin trong bộ nhớ.

Bộ nhớ RAM bao gồm hàng nghìn, hàng triệu bộ nhớ tuần tự (sequential storage) về địa điểm, mỗi địa điểm sẽ được định danh bằng một địa chỉ độc nhất - phạm vi từ 0 → max phụ thuộc vàa bộ nhớ được cài đặt

Trong C, khi khai báo 1 biến, trình biên dịch sẽ dành một vị trí độc nhất trong bộ nhớ cho biến đó. Biến đó sẽ được liên kết với địa chỉ đó. Khi gọi biến, nó sẽ tự động truy cập vị trí bộ nhớ thích hợp. Nhưng địa chỉ này bị ẩn đối với chúng ta

EX:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/aa2d2e31-0686-46c5-863f-ca057d7d1c22/Untitled.png)

Hình 9.1: biến rate được khởi tạo và gán giá trị bằng 100. Trình biên dịch đã dành bộ nhớ tại địa chỉ 1004 cho biến và liên kết rate với địa chỉ 1004

## **Creating a Pointer**

Để dễ hiểu hơn → Ta sẽ tạo một biến thứ 2 sẽ chứa địa chỉ của biến thứ nhất ( address của rate ) → Đặt tên cho nó là p_rate

Ex:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/8d919918-3731-4958-8353-353129bcae50/Untitled.png)

Lúc đầu, p_rate chưa được khởi tạo. Dung lượng lưu trữ đã được phân bổ cho p_rate, nhưng giá trị của nó chưa được xác định, như trong Hình 9.1

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/ec53b845-fb4f-481a-a1f9-e4c8fd659449/Untitled.png)

Bước tiếp theo ta sẽ chứa địa chỉ của biến rate trong biến p_rate. Bởi vì p_rate hiện tại đang chứa giá trị của rate, nó chỉ ra được nơi lưu trữ rate trong bộ nhớ

→ Ta nói p_rate trỏ vào rate (p_rate points to rate) 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/8b764164-0530-4b51-b537-b16e871841b0/Untitled.png)

Tóm lại, Con trỏ là biến chứa địa chỉ của biến khác

## **Declaring Pointers (Khởi tạo con trỏ)**

```c
typename *ptrname;
```

```c
char *ch1, *ch2; /* ch1 & ch2 both are pointers to type char */
float *value, percent; /* value is a pointer to type float, and
											 /* percent is an ordinary float variable *
```

### **Initializing Pointers**

Pointer chỉ được sử dụng khi nó trỏ vào địa chỉ của biến nào đó

```c
pointer = &variable;

```

EX:

```c
p_rate = &rate; /* assign the address of rate to p_rate */
```

Trước khi khởi tạo, p_rate không trỏ vào bất cứ điều gì . Sau khi khởi tạo, p_rate là một con trỏ của rate

### **Using Pointers**

EX:

```c
printf("%d", rate);

//can write

printf("%d", *p_rate);

//output
100

100
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/368297a8-9eed-431e-b5f6-960eac5848bf/Untitled.png)

```c
int var;
int *ptr;

var = 1;
ptr = &var;

printf("Direct access , var = %d", var);
printf("\nIndirect access , var = %d", *ptr);

printf("\nDirect address , var = %d", &var);
printf("\nIndirect address , var = %d", ptr);

//OutPut

Direct access , var = 1
Indirect access , var = 1

Direct address , var = 420005
Indirect address , var = 420005
```

NOTE:

KHÔNG sử dụng con trỏ chưa được khởi tạo cho đến khi chỉ định địa chỉ cho con trỏ đó . Kết quả rất rất rất rất kinh khủng 🫥

### **Pointers and Variable Types**

Mỗi kiểu dữ liệu của biến sẽ chiếm dung lượng khác nhau.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/f6548c44-308e-4744-b7d8-b1cdfbaf79d3/Untitled.png)

Mỗi byte bộ nhớ sẽ có các địa chỉ riêng, do đó một biến nhiều byte sẽ chiếm nhiều địa chỉ

Đối với Pointer, địa chỉ của một biến  thực chất là địa chỉ của byte đầu tiên mà nó giữ

EX:

```c
//khai bao bien
short vshort = 12225;
char vchar = 90;
float vfloat = 1200.2133;
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/78e4ac1b-68ca-452c-be7f-3a4325a1e445/Untitled.png)

```c
//khai bao pointer

int *p_vshort;
char *p_vchar;
float *p_vfloat;

p_vshort = &vshort;
p_vchar = &vchar;
p_vfloat = &vfloat;
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/818a10c7-9e65-4e19-9d33-6581d6227b87/Untitled.png)

### **Pointers and Arrays**

Tên mảng không có dấu ngoặc (array vs array[ ]) là một con trỏ

trỏ tới phần tử đầu tiên của mảng

Trong C

```c
data == &data[0]
```

→ Tên của mảng là một con trỏ tới mảng. Tên của mảng là pointer constant (hằng số con trỏ), do là hằng nên mang tính chất của hằng số

Nhưng ta có thể khai bao một biến con trỏ để trỏ vào mảng:

```c
int array[100], *p_array;

p_array = array;
```

Bởi vì p_array là con trỏ, nên nó có thể được điều chỉnh để trỏ tới bất kì đâu. không giống như tên mảng (array)

### **Array Element Storage**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/4c41623e-1d01-4105-8e0f-39cbf447e72a/Untitled.png)

### **Pointer Arithmetic**

Kiểu cho thấy sự linh hoạt giữa hằng số con trỏ (pointer constant) hay array name (array) với con trỏ trỏ vào array

```c

//pointer array
ptr_short++
```

→ từ array[0] → array[1]

Tuy nhiên dùng

```c
array++;
```

→ Lỗi

### **Array Subscript Notation and Pointers**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/73fcf41c-a06d-4563-9ba7-77b6c7df77b7/Untitled.png)

### **Passing Arrays to Functions**

Như ta đã biết, pointer tới array,  thì pointer đó chỉ biết được địa chỉ của phần từ đầu tiên của mảng. Nếu cho giá trị đó vào function thì function sẽ biết địa chỉ của array đó và có thể truy cập các phần tử của mảng bằng pointer..

Hãy xem xét một vấn đề khác. Nếu bạn viết một Function lấy một array làm đối số, bạn muốn một Function có thể xử lý các array có kích thước khác nhau. 

Vậy với cách đó làm sao Function có thể biết được kích thước của array.

Có 2 cách:

- Bạn có thể xác định phần tử mảng cuối cùng bằng cách lưu trữ một giá trị đặc biệt ở đó. Khi hàm xử lý mảng, nó sẽ tìm giá trị đó trong mỗi phần tử.

```c
/* Passing an array to a function. */
#include <stdio.h>

#define MAX 10

int array[MAX], count;

int largest(int num_array[], int length);

int main(void)
{
    /* Input MAX values from the keyboard. */
    for (count = 0; count < MAX; count++)
    {
        printf("Enter an integer value: ");
        scanf("%d", &array[count]);
    }

    /* Call the function and display the return value. */
    printf("\n\nLargest value = %d\n", largest(array, MAX));

    return 0;
}

/* Function largest() returns the largest value in an integer array */
int largest(int num_array[], int length)
{
    int count, biggest = -12000;

    for (count = 0; count < length; count++)
    {
        if (num_array[count] > biggest)
            biggest = num_array[count];
    }

    return biggest;
}
```

- Truyền cho hàm kích thước mảng làm đối số. Đây có thể là một đối số kiểu int đơn giản. Do đó, hàm được truyền hai đối số: một con trỏ tới phần tử mảng đầu tiên và một số nguyên xác định số phần tử trong mảng

```c
//* Passing an array to a function. Alternative way. */
#include <stdio.h>

#define MAX 10

int array[MAX + 1], count;

int largest(int num_array[]);

int main(void)
{
    /* Input MAX values from the keyboard. */
    for (count = 0; count < MAX; count++)
    {
        printf("Enter an integer value: ");
        scanf("%d", &array[count]);

        if (array[count] == 0)
        {
            count = MAX; /* will exit for loop */
        }
    }

    array[MAX] = 0;

    /* Call the function and display the return value. */
    printf("\n\nLargest value = %d\n", largest(array));

    return 0;
}

/* Function largest() returns the largest value in an integer array */
int largest(int num_array[])
{
    int count, biggest = -12000;

    for (count = 0; num_array[count] != 0; count++)
    {
        if (num_array[count] > biggest)
        {
            biggest = num_array[count];
        }
    }

    return biggest;
}
```

**Declaring Pointers to Pointers**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/73ee85fd-54a8-42cc-8f1d-460966cba6fa/Untitled.png)

## **Working with Arrays of Pointers**

### **Strings and Pointers**

```c
char messsage[] = "this is the message,"
//can write
char *message = "this is the message"
```

Cả hai khai báo đều tương đương. Trong mỗi trường hợp, trình biên dịch phân bổ đủ không gian để giữ chuỗi cùng với ký tự null kết thúc của nó và thông báo biểu thức là một con trỏ tới điểm bắt đầu của chuỗi. 

Nhưng còn hai khai báo sau thì khác

```c
char message1[20];
char *message2;
```

Dòng đầu tiên khai báo array kiểu char với 20 ký tự, pointer sẽ trỏ vào vị trí đầu tiên của array

Dòng thứ 2, khai báo con trỏ kiểu char.  Không phân bổ không gian lưu trữ cho một chuỗi—chỉ có không gian để giữ con trỏ.

→ Nếu muốn tạo một chuỗi và sau đó có message2 trỏ tới chuỗi đó, trước tiên  phải phân bổ không gian cho chuỗi đó. Dùng  malloc() cho mục đích này

### **Declaring an Array of Pointers to Type**
 char

```c
char *message [10];
//or
char *message[10] = { “one”, “two”, “three” };
```

[]()

### **Pulling Things Together With an Example**

```c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

#define MAXLINES 25

int get_lines(char *lines[]);
void sort(char *p[], int n);
void print_strings(char *p[], int n);

char *lines[MAXLINES];

int main(void) {
    int number_of_lines;

    /* Read in the lines from the keyboard. */
    number_of_lines = get_lines(lines);

    if (number_of_lines < 0) {
        puts("Memory allocation error");
        exit(-1);
    }

    sort(lines, number_of_lines);
    print_strings(lines, number_of_lines);

    return 0;
}

int get_lines(char *lines[]) {
    int n = 0;
    char buffer[80];

    puts("Enter one line at a time; enter a blank line when done.");

    while ((n < MAXLINES) && (fgets(buffer, sizeof(buffer), stdin) != NULL) && (buffer[0] != '\0')) {
        if ((lines[n] = (char *)malloc(strlen(buffer) + 1)) == NULL) {
            return -1;
        }
        strcpy(lines[n++], buffer);
    }

    return n;
}

void sort(char *p[], int n) {
    int a, b;
    char *tmp;

    for (a = 1; a < n; a++) {
        for (b = 0; b < n - 1; b++) {
            if (strcmp(p[b], p[b + 1]) > 0) {
                tmp = p[b];
                p[b] = p[b + 1];
                p[b + 1] = tmp;
            }
        }
    }
}

void print_strings(char *p[], int n) {
    int count;

    for (count = 0; count < n; count++)
        printf("%s\n", p[count]);
}
```

EX

```c
while ((n < MAXLINES) && (gets(buffer) != 0) && (buffer[0] != ‘\0’))
```

Điều kiện while có 3 phần. Phần đầu tiên, n < MAXLINES, đảm bảo rằng số dòng tối đa được nhập vào ko lớn hơn 25. Phần thứ hai, gets(buffer) != 0, gọi hàm thư viện gets() để đọc một dòng từ bàn phím vào bộ đệm và xác minh rằng lỗi cuối tệp hoặc một số lỗi khác không xảy ra. Phần thứ ba, buffer[0] != '\0', xác minh rằng ký tự đầu tiên của dòng vừa nhập không phải là ký tự null, điều này sẽ báo hiệu rằng một dòng trống đã được nhập.

```c
if ((lines[n] = (char *)malloc(strlen(buffer)+1)) == NULL)
```

Câu lệnh này gọi malloc() để phân bổ không gian cho chuỗi vừa được nhập vào. 

Hàm strlen() trả về độ dài của chuỗi được truyền dưới dạng đối số; giá trị được tăng thêm 1 để malloc() phân bổ không gian cho chuỗi cộng với ký tự null kết thúc của nó. 

(char *), ngay trước malloc() trên dòng 44, là một kiểu dữ liệu chỉ định loại con trỏ được trả về bởi malloc(), trong trường hợp này là một con trỏ để gõ char. ⇒ n malloc() trả về một con trỏ. Câu lệnh gán giá trị của con trỏ được trả về bởi malloc() cho phần tử tương ứng của mảng con trỏ. Nếu malloc() trả về NULL, vòng lặp if trả về việc thực thi chương trình đang gọi với giá trị trả về là -1. Mã trong main() kiểm tra giá trị trả về của get_lines() và kiểm tra xem giá trị có nhỏ hơn 0 có được trả về hay không; dòng 23 đến 27 báo cáo lỗi cấp phát bộ nhớ và chấm dứt chương trình.

Nếu việc cấp phát bộ nhớ thành công, chương trình sẽ sử dụng hàm strcpy() trên dòng 46 để sao chép chuỗi từ bộ đệm vị trí lưu trữ tạm thời vào không gian lưu trữ vừa được cấp phát bởi malloc(). Vòng lặp while sau đó lặp lại, nhận một dòng đầu vào khác

Sau khi trả giá trị về cho main từ get_line

- Một số dòng văn bản đã được đọc từ bàn phím và được lưu trong bộ nhớ dưới dạng chuỗi kết thúc bằng null
- Mảng lines[] chứa con trỏ tới tất cả các chuỗi. Thứ tự của các con trỏ trong mảng là thứ tự các chuỗi được nhập vào
- Biến number_of_lines chứa số dòng được nhập

```c
    number_of_lines = get_lines(lines);
```

```c
void sort(char *p[], int n) {
    int a, b;
    char *tmp;

    for (a = 1; a < n; a++) {
        for (b = 0; b < n - 1; b++) {
            if (strcmp(p[b], p[b + 1]) > 0) {
                tmp = p[b];
                p[b] = p[b + 1];
                p[b + 1] = tmp;
            }
        }
    }
}
```

⇒ thật ra hàm sort này,không di chuyển các chuỗi string, mà chỉ di chuyển thứ tự của các con trỏ trong mảng Lines[]

Vòng lặp bên ngoài thực thi number_of_lines - 1 lần. Mỗi lần vòng lặp bên ngoài thực thi, vòng lặp bên trong sẽ duyệt qua mảng con trỏ, so sánh (chuỗi n) và (chuỗi n+1) từ n = 0 tới n = number_of_lines - 1. Việc so sánh được thực hiện bởi hàm thư viện strcmp() 

Trong chương trình, giá trị trả về từ strcmp() lớn hơn 0 có nghĩa là chuỗi đầu tiên "lớn hơn" chuỗi thứ hai và chúng phải được hoán đổi (nghĩa là các con trỏ của chúng trong dòng[] phải được hoán đổi). Việc này được thực hiện bằng cách sử dụng biến tạm thời tmp. Các dòng từ 63 đến 65 thực hiện hoán đổi

[]()

## **Working with Pointers to Functions**

```c
type (*ptr_to_func)(parameter_list);
```

```c
int (*func1)(int x);
void (*func2)(double y, double z);
char (*func3)(char *p[]);
void (*func4)();
```

1. Là pointer to funtion dạng int và trả về kiểu int
2. pointer to funtion lấy 2 giá trị double, và ko trả kiểu
3. pointer to funtion lấy một mảng con trỏ char làm đối số của nó và trả về kiểu char
4. Ko lấy gì cả

⇒ sử dụng () 

### **Initializing and Using a Pointer to a Function**

```c
float square(float x); // The function prototype.
float (*ptr)(float x); // The pointer declaration.
float square(float x) // The function definition
{
return x;
}
```

Vì square vs ptr cùng tham số và kiểu:
⇒

```c
ptr = square
```

⇒ có thể gọi function sử dụng pointer bằng cách

```c
answer = ptr (X);
```

EX

```c
/* Demonstration of declaring and using a pointer to a function.*/

#include <stdio.h>

/* The function prototype. */
double square(double x);

/* The pointer declaration. */
double (*ptr)(double x);

int main(void) {
    /* Initialize p to point to square(). */
    ptr = square;

    /* Call square() two ways. */
    printf("%f %f\n", square(6.6), ptr(6.6));
    return 0;
}

double square(double x) {
    return x * x;
}
```

## LINKED LIST

Có nhiều loại Linked lists

- single - linked lists
- double - linked lists
- binary trees

Mỗi mục dữ liệu trong linked list được chứa trong một cấu trúc.  Cấu trúc lại chứa các phần tử dữ liệu (data elements) cần thiết để chứa dữ liệu đang được lưu trữ; những điều này phụ thuộc vào nhu cầu của chương trình cụ thể. Ngoài ra, còn có một thành phần dữ liệu nữa—con trỏ. Con trỏ này cung cấp các liên kết trong danh sách liên kết. 

EX:

```c
struct person 
{
	char name[20]
	struct person *next;
};

```

Mã này định nghĩa một cấu trúc có tên là người. Người chỉ chứa một mảng ký tự 20 phần tử. Struct person cũng chứa một con trỏ đến kiểu person 

⇒ Có nghĩa mỗi **struct person không chỉ chứa một đoạn data, mà nó còn trỏ đến struct person khác**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/0405180e-7d63-46f4-9d14-7663976298ab/Untitled.png)

mỗi Struct person sẽ chỏ đến cái tiếp theo, và phần tử cuối sẽ là con trỏ trỏ tới giá trị NULL

Còn Thành phần đầu tiên của linked list được xác định bởi head pointer ⇒ luôn luôn trỏ vào thành phần tử đầu tiên của linked list ⇒ Và phần tử đầu sẽ trỏ vào phần tử thứ 2 ⇒ cho đến khi gặp phần tử có con trỏ là NULL

- Nếu Linked list rỗng, thì head pointer = NULL

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/d5d6db24-1658-4b47-8f7c-4f9a14304e99/Untitled.png)

- Head pointer khi list chưa bắt đầu, và sau khi bắt đầu

### **Working with Linked Lists**

Trước tiên tạo struct

```c
struct person {
char name[20];
struct person *next;
};
struct person *new;
struct person *head;
head = NULL;
```

### **Adding an Element to the Beginning of a List**

Có 2 trường hợp

- Nếu head pointer = NULL, và thành viên duy nhất là phần tử mới

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/20abc808-b04b-48b6-acb1-b081b06b1a17/Untitled.png)

- Nếu head pointer ≠Null, List đang chứa 1 or n phần tử.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/df5d0364-07ed-4ce1-8cc8-b870ecb43c65/Untitled.png)

⇒ Tuy nhiên cách thêm phần tử mới vào đầu danh sách vẫn giống nhau

1. Tạo mộtstructure, phân bổ không gian bộ nhớ bằng cách sử dụng malloc(). 
2. Đặt next pointer của phần tử mới thành giá trị hiện tại của head pointer. Giá trị này sẽ là NULL nếu danh sách trống hoặc địa chỉ của phần tử đầu tiên hiện tại nếu không.
3. Tạo con trỏ head trỏ tới phần tử mới

```c
new = (person*)malloc(sizeof(struct person));
new->next = head;
head = new;
```

### **Adding an Element to the End of the List**

Chạy từ *head pointer → cuối danh sách* để tìm phần tử cuối

1. Tạo Struct, sử dụng malloc()
2. Đặt next pointer của phần tử cuối trỏ tới phần tử mới (địa chỉ được trả về bởi malloc() )
3. Đặt next pointer vào phần tứ mới trỏ tới NULL làm dấu hiệu là phần tử cuối

```c
person *current;
....
current = head;
while (current->next != NULL)
	current = current -> next;
new = (person*)malloc(sizeof(struct person));
current->next =new;
new->next = NULL;

```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/7f1f0c58-0cf9-4e7b-8d54-e5ca6c94c847/Untitled.png)

### Adding an Element to the Middle of the List

Phổ biến nhất 

Cần phải biết nơi phần tử mới được thêm vào 

1. Trong danh sách, xác định vị trí phần tử hiện có mà phần tử mới sẽ được đặt sau. Đây là phần tử đánh dấu.
2. Tạo Struct, sử dụng malloc()
3. Đặt next pointer của phần tử đánh dấu trỏ tới phần tử mới (địa chỉ được trả về bởi malloc())
4. Đặt next pointer của phần tử mới trỏ đến phần tử mà phần tử đánh dấu đang trỏ

```c
person *marker;
/* Code here to set marker to point to the desired list location. */
...
new = (LINK)malloc(sizeof(PERSON));
new->next = marker->next;
marker->next = new;
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/87800bfa-9c07-4cb3-b34d-d3799391d2c1/Untitled.png)

### Deleting an Element from the List

1. Xóa phần tử đầu, chỉnh head pointer trỏ tới phần tử thứ 2 của list

```c
free(head)
head = head -> next;
```

1. Xóa phần tử cuối, chỉnh next pointer của phần tử tiếp theo thành NULL

```c
person *current1, *current2;
current1 = head;
current2 = current1 -> next;
while (current2->next != NULL)
{
current1 = current2;
current2 = current1 ->next;
}
free (current1 -> next)
current1 -> next=null;
if (head=current1)
		head = null
```

1. Để xóa bất kỳ phần tử nào khác, hãy đặt con trỏ tiếp theo của phần tử trước phần tử bị xóa để trỏ đến phần tử sau phần tử bị xóa.

```c
person *current1, *current2;
/* Code goes here to have current1 point to the */
/* element just before the one to be deleted. */
current2 = current1->next;
free(current1->next);
current1->next = current2->next
```

Bộ nhớ của phần tử bị xóa khỏi list sẽ được giải phóng, để chương trình không yêu cầu nhiều bộ nhớ hơn mức cần thiết (memory leak)

sử dụng free()function, 

**A Simple Linked List Demonstration**

1. It defines a structure and the required pointers for the list.

2. It adds the first element to the list.

3. It adds an element to the end of the list.

4. It adds an element to the middle of the list.

5. It displays the list contents on-screen

```c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

// The list data structure.
struct data {
    char name[20];
    struct data *next;
};

// Define typedefs for the structure
// and a pointer to it.
typedef struct data PERSON;
typedef PERSON *LINK;

int main(void) {
    // Head, new, and current element pointers.
    LINK head = NULL;
    LINK new_person = NULL;
    LINK current = NULL;

    // Add the first list element. We do not
    // assume the list is empty, although in
    // this demo program it always will be.
    new_person = (LINK)malloc(sizeof(PERSON));
    new_person->next = head;
    head = new_person;
    strcpy(new_person->name, "Abigail");

    // Add an element to the end of the list.
    // We assume the list contains at least one element.
    current = head;
    while (current->next != NULL) {
        current = current->next;
    }

    new_person = (LINK)malloc(sizeof(PERSON));
    current->next = new_person;
    new_person->next = NULL;
    strcpy(new_person->name, "Carolyn");

    // Add a new element at the second position in the list.
    new_person = (LINK)malloc(sizeof(PERSON));
    new_person->next = head->next;
    head->next = new_person;
    strcpy(new_person->name, "Beatrice");

    // Print all data items in order.
    current = head;
    while (current != NULL) {
        printf("\n%s", current->name);
        current = current->next;
    }

    printf("\n");

    return 0;
}
```

### **Implementing a Linked List**

```c
/**/

#include <stdio.h>
#include <stdlib.h>

#ifndef NULL
#define NULL 0
#endif

struct list {
    int ch;                // Using an int to hold a char
    struct list *next_rec; // Pointer to the next record in the list
};

typedef struct list LIST;
typedef LIST *LISTPTR;

LISTPTR add_to_list(int ch, LISTPTR first);
void show_list(LISTPTR);
void free_memory_list(LISTPTR);

int main(void) {
    LISTPTR first = NULL; // head pointer
    int i = 0;
    int ch;
    char trash[256]; // to clear stdin buffer.

    while (i++ < 5) // build a list based on 5 items given
    {
        ch = 0;
        printf("\nEnter character %d, ", i);

        do {
            printf("\nMust be a to z: ");
            ch = getc(stdin); // get next char in buffer
            gets(trash);      // remove trash from buffer
        } while ((ch < 'a' || ch > 'z') && (ch < 'A' || ch > 'Z'));

        first = add_to_list(ch, first);
    }

    show_list(first);       // Dumps the entire list
    free_memory_list(first); // Release all memory
    return 0;
}

LISTPTR add_to_list(int ch, LISTPTR first) {
    LISTPTR new_rec = NULL; // Holds address of new rec
    LISTPTR tmp_rec = NULL; // Hold tmp pointer
    LISTPTR prev_rec = NULL;

    // Allocate memory.
    new_rec = (LISTPTR)malloc(sizeof(LIST));
    if (!new_rec) // Unable to allocate memory
    {
        printf("\nUnable to allocate memory!\n");
        exit(1);
    }

    // Set new link’s data
    new_rec->ch = ch;
    new_rec->next_rec = NULL;

    if (first == NULL) // adding the first link to the list
    {
        first = new_rec;
        new_rec->next_rec = NULL; // redundant but safe
    } else // not the first record
    {
        // See if it goes before the first link
        if (new_rec->ch < first->ch) {
            new_rec->next_rec = first;
            first = new_rec;
        } else // it is being added to the middle or end
        {
            tmp_rec = first->next_rec;
            prev_rec = first;

            // Check to see where the link is added
            if (tmp_rec == NULL) {
                // We are adding the second record to the end
                prev_rec->next_rec = new_rec;
            } else {
                // Check to see if adding in the middle
                while (tmp_rec->next_rec != NULL) {
                    if (new_rec->ch < tmp_rec->ch) {
                        new_rec->next_rec = tmp_rec;
                        if (new_rec->next_rec != prev_rec->next_rec) {
                            printf("ERROR");
                            getc(stdin);
                            exit(0);
                        }
                        prev_rec->next_rec = new_rec;
                        break; // link is added; exit while
                    } else {
                        tmp_rec = tmp_rec->next_rec;
                        prev_rec = prev_rec->next_rec;
                    }
                }

                // Check to see if adding to the end
                if (tmp_rec->next_rec == NULL) {
                    if (new_rec->ch < tmp_rec->ch) // 1 b4 end
                    {
                        new_rec->next_rec = tmp_rec;
                        prev_rec->next_rec = new_rec;
                    } else // at the end
                    {
                        tmp_rec->next_rec = new_rec;
                        new_rec->next_rec = NULL; // redundant
                    }
                }
            }
        }
    }
    return first;
}

void show_list(LISTPTR first) {
    LISTPTR cur_ptr;
    int counter = 1;

    printf("\n\nRec addr Position Data Next Rec addr\n");
    printf("======== ======== ==== =============\n");

    cur_ptr = first;
    while (cur_ptr != NULL) {
        printf(" %p ", (void *)cur_ptr);
        printf(" %2i %c", counter++, cur_ptr->ch);
        printf(" %p \n", (void *)cur_ptr->next_rec);
        cur_ptr = cur_ptr->next_rec;
    }
}

void free_memory_list(LISTPTR first) {
    LISTPTR cur_ptr, next_rec;
    cur_ptr = first; // Start at the beginning

    while (cur_ptr != NULL) // Go while not end of the list
    {
        next_rec = cur_ptr->next_rec; // Get the address of the next record
        free(cur_ptr);                // Free the current record
        cur_ptr = next_rec;           // Adjust the current record
    }
}
```

# DAY 16: USING DISK FILES

Opening file

```c
FILE *fopen(const char *filename, const char *mode);
```

Nếu ko mở được ⇒ return NULL

| mode | Meaning |
| --- | --- |
| r | Mở tập tin để đọc. Nếu file không tồn tại, fopen() trả về NULL |
| w | Mở tập tin để viết. Nếu một tập tin có tên được chỉ định không tồn tại, nó sẽ được tạo. Nếu một tệp có tên được chỉ định tồn tại, nó sẽ bị xóa mà không có cảnh báo và một tệp mới, trống sẽ được tạo |
| a | Mở tập tin để nối thêm. Nếu một tập tin có tên được chỉ định không tồn tại, nó sẽ được tạo. Nếu tệp tồn tại, dữ liệu mới sẽ được thêm vào cuối tệp |
| r+ | Mở tập tin để đọc và ghi. Nếu một tập tin có tên được chỉ định không tồn tại, nó sẽ được tạo. Nếu tệp tồn tại, dữ liệu mới sẽ được thêm vào đầu tệp, ghi đè dữ liệu hiện có |
| w+ | Mở tập tin để đọc và ghi. Nếu một tập tin có tên được chỉ định không tồn tại, nó sẽ được tạo. Nếu tập tin tồn tại, nó sẽ bị ghi đè |
| a+ | Mở một tập tin để đọc và nối thêm. Nếu một tập tin có tên được chỉ định không tồn tại, nó sẽ được tạo. Nếu tệp tồn tại, dữ liệu mới sẽ được thêm vào cuối tệp. |

```c
#include <stdlib.h>
#include <stdio.h>

int main(void) {
    FILE *fp;
    char ch, filename[40], mode[4];

    while (1) {
        /* Input filename and mode. */
        printf("\nEnter a filename: ");
        gets(filename);
        printf("\nEnter a mode (max 3 characters): ");
        gets(mode);

        /* Try to open the file. */
        if ((fp = fopen(filename, mode)) != NULL) {
            printf("\nSuccessful opening %s in mode %s.\n", filename, mode);
            fclose(fp);
            puts("Enter x to exit, any other to continue.");
            if ((ch = getc(stdin)) == 'x')
                break;
            else
                continue;
        } else {
            fprintf(stderr, "\nError opening file %s in mode %s.\n", filename, mode);
            puts("Enter x to exit, any other to try again.");
            if ((ch = getc(stdin)) == 'x')
                break;
            else
                continue;
        }
    }
    return 0;
}
```

## **Formatted File Input and Output**

### Formatted File Output

```c
int fprintf(FILE *fp, char *fmt, ...);
```

### Formatted File Input

```c
int fscanf(FILE *fp, const char *fmt,...);
```

```c
/* Reading formatted file data with fscanf(). */
#include <stdlib.h>
#include <stdio.h>

int main(void) {
    float f1, f2, f3, f4, f5;
    FILE *fp;

    if ((fp = fopen("INPUT.TXT", "r")) == NULL) {
        fprintf(stderr, "Error opening file.\n");
        exit(1);
    }

    fscanf(fp, "%f %f %f %f %f", &f1, &f2, &f3, &f4, &f5);
    printf("The values are %f, %f, %f, %f, and %f\n", f1, f2, f3, f4, f5);

    fclose(fp);
    return 0;
}
```

## **Character Input and Output**

### Character Input

```c
getc()
fgetc() //single character;
fgets() //for lines
```

getc() vs fgetc() có thể thay thế cho nhau

```c
int getc(FILE *fp);
```

Vì sao 2 cái đều trả về giá trị là single character, nhưng lại dùng kiểu int ⇒ do là khi đọc tệp, bạn cần có khả năng đọc được điểm đánh dấu cuối tệp, trên một số hệ thống không phải là kiểu char mà là kiểu int.

Fgets()

```c
char *fgets(char *str, int n, FILE *fp);
```

### Character Output

putc() và fputc():
Thư viện hàm fputc() và putc() ghi một ký tự đơn vào một luồng được chỉ định. 

```c
int putc(int ch, FILE *fp);
```

ch là ký tự cần xuất.  Đối số fp là con trỏ liên kết với tệp (con trỏ được trả về bởi fopen() khi tệp được mở). Hàm putc() trả về ký tự vừa viết (nếu thành công) hoặc EOF (nếu xảy ra lỗi). Hằng số ký hiệu EOF được định nghĩa trong stdio.h và nó có giá trị -1. Vì không có ký tự "thực" nào có giá trị số đó nên EOF có thể được sử dụng làm chỉ báo lỗi (chỉ với các tệp chế độ văn bản).

fputs():

Để ghi một dòng ký tự vào một luồng, hãy sử dụng hàm thư viện fputs(). Hàm này hoạt động giống như put(), .Điểm khác biệt duy nhất là với fputs() có thể chỉ định luồng đầu ra

```c
char fputs(char *str, FILE *fp);
```

## **Direct File Input and Output**

### The fwrite () function

 ghi một khối dữ liệu từ bộ nhớ vào tệp chế độ nhị phân.

```c
int fwrite(void *buf, int size, int count, FILE *fp)
```

Đối số buf là một con trỏ tới vùng bộ nhớ chứa dữ liệu được ghi vào tệp. Kiểu con trỏ là void; nó có thể là một con trỏ tới bất cứ điều gì. 

size  tính bằng byte, của các mục dữ liệu riêng lẻ và số lượng chỉ định số lượng mục được ghi. 

Ví dụ: nếu bạn muốn lưu một mảng số nguyên 100 phần tử, kích thước sẽ là 2 (vì mỗi int chiếm 2 byte) và count sẽ là 100 (vì mảng chứa 100 phần tử). Để lấy đối số kích thước, bạn có thể sử dụng toán tử sizeof()

```c
//check error
if( (fwrite(buf, size, count, fp)) != count)
fprintf(stderr, “Error writing to file.”);

//Example
fwrite(&x, sizeof(double), 1, fp);
```

### The fread() Function

đọc một khối dữ liệu từ tệp chế độ nhị phân vào bộ nhớ.

```c
int fread(void *buf, int size, int count, FILE *fp)
```

CODE FOR FREAD & FWRITE

```c
/* Direct file I/O with fwrite() and fread(). */
#include <stdlib.h>
#include <stdio.h>

#define SIZE 20

int main(void) {
    int count, array1[SIZE], array2[SIZE];
    FILE *fp;

    /* Initialize array1[]. */
    for (count = 0; count < SIZE; count++)
        array1[count] = 2 * count;

    /* Open a binary mode file. */
    if ((fp = fopen("direct.txt", "wb")) == NULL) {
        fprintf(stderr, "Error opening file.");
        exit(1);
    }

    /* Save array1[] to the file. */
    if (fwrite(array1, sizeof(int), SIZE, fp) != SIZE) {
        fprintf(stderr, "Error writing to file.");
        exit(1);
    }

    fclose(fp);

    /* Now open the same file for reading in binary mode. */
    if ((fp = fopen("direct.txt", "rb")) == NULL) {
        fprintf(stderr, "Error opening file.");
        exit(1);
    }

    /* Read the data into array2[]. */
    if (fread(array2, sizeof(int), SIZE, fp) != SIZE) {
        fprintf(stderr, "Error reading file.");
        exit(1);
    }

    fclose(fp);

    /* Now display both arrays to show they’re the same. */
    for (count = 0; count < SIZE; count++)
        printf("%d\t%d\n", array1[count], array2[count]);

    return 0;
}
```

# DAY 17: MANIPULATING STRINGS

 trong chương trình C, một chuỗi là một chuỗi các ký tự, với phần đầu được biểu thị bằng một con trỏ và phần cuối của chuỗi được đánh dấu bằng ký tự null \0.

Có thể biết độ dài của Strings sữ dụng library function

```c
size_t strlen(char *str);
```

⇒ size_t trả về số nguyên ko dấu

```c
/* Using the strlen() function. */
#include <stdio.h>
#include <string.h>

int main(void) {
    size_t length;
    char buf[80];

    while (1) {
        puts("\nEnter a line of text, a blank line to exit.");
        gets(buf);

        length = strlen(buf);

        if (length != 0)
            printf("\nThat line is %lu characters long.", length);
        else
            break;
    }

    return 0;
}
```

## **Copying Strings**

### The strcpy () Function

Hàm thư viện strcpy() sao chép toàn bộ chuỗi sang một vị trí bộ nhớ khác. bao gồm cả “\0”

```c
char *strcpy( char *destination, const char *source );
```

Giá trị trả về là một con trỏ tới chuỗi mới, destination.

Khi sử dụng strcpy(), trước tiên bạn phải phân bổ không gian lưu trữ cho chuỗi đích. Hàm này không có cách nào để biết liệu đích có trỏ đến không gian được phân bổ hay không. Nếu không gian chưa được phân bổ, hàm sẽ ghi đè byte bộ nhớ strlen(nguồn), bắt đầu từ đích. ⇒ TOANG

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char source[] = "The source string.";

int main(void) {
    char dest1[80];
    char *dest2, *dest3;

    printf("\nsource: %s", source);

    /* Copy to dest1 is okay because dest1 points to */
    /* 80 bytes of allocated space. */
    strcpy(dest1, source);
    printf("\ndest1: %s", dest1);

    /* To copy to dest2 you must allocate space. */
    dest2 = (char *)malloc(strlen(source) + 1);
    strcpy(dest2, source);
    printf("\ndest2: %s\n", dest2);

    /* Copying without allocating destination space is a no-no. */
    /* The following could cause serious problems. */
    /* strcpy(dest3, source); */

    return 0;
}
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/40f092c2-bf3f-4e9d-9af8-458a4c1daaf0/Untitled.png)

### The strncpu () function

Giống strcpy, nhưng cho phép copy số lượng ký tự

```c
char *strncpy(char *destination, const char *source, size_t n);
```

```c

```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/007d6ca0-3954-43d6-8ba7-8690baf39db7/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/e751fc74-bece-4352-a799-a71669c5e72a/Untitled.png)

### The strdup() function

 strdup() tương tự như strcpy(), ngoại trừ việc strdup() thực hiện cấp phát bộ nhớ riêng cho chuỗi đích bằng lệnh gọi malloc(). T

rên thực tế, Nó thực hiễn những gì có trong đoạn code của strcpy, phân bổ không gian với malloc() và sau đó gọi strcpy().

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/61c2cad5-84a7-4f87-851c-1f865db3bc4c/Untitled.png)

## **Concatenating Strings**

Nối chuỗi

The strcat () Function

```c
char *strcat(char *str1, const char *str2);
```

Copy str2 vào cuối của str1, cũng di chuyển ‘\0’

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/9ac787ad-1bc7-484d-94b1-71cb0d4848f6/Untitled.png)

The strncat() Function
Hàm thư viện strncat() cũng thực hiện nối chuỗi nhưng nó cho phép  chỉ định số lượng ký tự của chuỗi nguồn được thêm vào cuối chuỗi đích. 

```c
char *strncat(char *str1, const char *str2, size_t n);
```

Nếu str2 chứa nhiều hơn n ký tự thì n ký tự đầu tiên sẽ được thêm vào cuối str1. 

Nếu str2 chứa ít hơn n ký tự thì toàn bộ str2 sẽ được thêm vào cuối str1. 

Trong cả hai trường hợp, ký tự null kết thúc được thêm vào cuối chuỗi kết quả.  Phải phân bổ đủ không gian cho str1 để chứa chuỗi kết quả. 

```c
/* The strncat() function. */

#include <stdio.h>
#include <string.h>

char str2[] = "abcdefghijklmnopqrstuvwxyz";

int main(void) {
    char str1[27];
    int n;

    for (n = 1; n < 27; n++) {
        strcpy(str1, "");
        strncat(str1, str2, n);
        puts(str1);
    }

    return 0;
}
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/7f2f0fbd-4b14-42f7-a82f-64bd4cd79d15/Untitled.png)

```c
strcpy(str1, " ")';
```

Dòng này sao chép vào str1 một chuỗi trống chỉ bao gồm một ký tự NULLduy nhất. Kết quả là ký tự đầu tiên trong str1—str1[0]—được đặt bằng 0 (ký tự null). Điều tương tự có thể được thực hiện với các câu lệnh str1[0] = 0; hoặc str1[0] = ‘\0’;.

## **Comparing Strings**

So sánh chuỗi

### strcmp

```c
int strcmp(const char *str1, const char *str2);

x = strcmp(str1, str2);
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/0c01afe9-2aa5-456d-923f-3270f26a4283/Untitled.png)

### strncmp

```c
int strncmp(const char *str1, const char *str2, size_t n);

x = strncmp(str1, str2, n);
```

So sánh giá trị trong bảng ASCII’

## **Searching Strings**

### strchr()

tìm sự xuất hiện đầu tiên của một ký tự được chỉ định trong chuỗi

```c
char *strchr(constchar *str, int ch);

//ex 
strchr(buf, ch);
```

### strrchr()

tìm sự xuất hiện cuối cùng trong chuỗi

```c
char *strrchr(const char *str, int ch);
```

### strcspn()

Hàm strcspn() bắt đầu tìm kiếm ở ký tự đầu tiên của str1, tìm kiếm bất kỳ ký tự riêng lẻ nào có trong str2. 

Hàm không tìm chuỗi str2 mà chỉ tìm các ký tự chứa trong đó. Nếu hàm tìm thấy kết quả khớp, nó sẽ trả về giá trị offset từ đầu str1 nơi chứa ký tự khớp. Nếu không tìm thấy kết quả khớp, strcspn() trả về giá trị của strlen(str1). Điều này chỉ ra rằng kết quả khớp đầu tiên là ký tự null kết thúc chuỗi. 

```c
size_t strcspn(const char *str1, const char *str2);
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/7f93b6c0-8996-4367-be64-c2ff5e5cf8c7/Untitled.png)

### strspn()

```c
size_t strspn(const char *str1, const char *str2)
```

tìm kiếm str1, so sánh từng ký tự với các ký tự có trong str2. Nó trả về vị trí của ký tự đầu tiên trong str1 không khớp với ký tự trong str2. Nói cách khác, strspn() trả về độ dài của đoạn đầu tiên của str1 bao gồm toàn bộ các ký tự tìm thấy trong str2. Kết quả trả về là 0 nếu không có ký tự nào khớp.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/24da2043-298a-482c-8c19-f2722b219940/Untitled.png)

## **String Conversions**

```c
char *strlwr(char *str); //convert all letter upper to lower
char *strupr(char *str); //convert all letter lower to upper
```

## **Miscellaneous String Functions**

strrev(): đảo ngược thứ tự của tất cả các ký tự trong chuỗi

```c
char *strrev(char *str);
```

strset() **and** strnset()

Hàm strset() thay đổi tất cả các ký tự trong str thành ch ngoại trừ ký tự null kết thúc. 

Hàm strnset() thay đổi n ký tự đầu tiên của str thành ch. Nếu n >= strlen(str), strnset() thay đổi tất cả các ký tự trong str. Liệt kê 17.14 thể hiện cả hai hàm’

```c
char *strset(char *str, int ch);
char *strnset(char *str, int ch, size_t n);
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/846271a4-26cf-492d-b2e8-876786f296e4/Untitled.png)

## **String-to-Number Conversions**

### **Converting Strings To Integers**

```c
int atoi(const char *ptr);
```

**Strings To Integers** . Ngoài các chữ số, chuỗi có thể chứa khoảng trắng ở đầu và dấu + hoặc –. Quá trình chuyển đổi bắt đầu ở đầu chuỗi và tiếp tục cho đến khi gặp một ký tự không thể chuyển đổi 

(ví dụ: một chữ cái hoặc dấu chấm câu). Số nguyên kết quả được trả về chương trình gọi. Nếu không tìm thấy ký tự chuyển đổi nào, atoi() trả về 0. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/57a2672f-e3e4-4774-8b4c-4cfd8a738db4/Untitled.png)

**Converting Strings to Longs**

```c
long atol(const char *ptr);
```

**Converting Strings to Long Longs**

```c
long long atoll(const char *ptr);
```

**Converting Strings to Floating Point Numeric Values**

```c
double atof(const char *str);
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/d8fa4ab4-b0e9-416e-a66d-b4799dbe2d26/Untitled.png)

# DAY  18: GETTING MORE FROM FUNCTIONS

## **Passing Pointers to Functions**

Điểm chính là nếu một biến được truyền làm đối số thì mã trong hàm không thể sửa đổi giá trị của biến đó. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/aaf1e4b9-17ca-46d9-95a0-7b9c8140937e/Untitled.png)

Trong trường hợp này, đối số là một biến kiểu int đơn giản, nhưng nguyên tắc giống nhau đối với các kiểu biến khác

Khi một biến được truyền cho một hàm theo giá trị, hàm đó có quyền truy cập vào giá trị của biến đó nhưng không truy cập vào bản sao gốc của biến đó. 

Kết quả là mã trong hàm không thể sửa đổi biến ban đầu. Đây là lý do chính tại sao truyền theo giá trị là phương pháp truyền đối số mặc định: Dữ liệu bên ngoài hàm được bảo vệ khỏi sửa đổi vô ý

Có một cách khác để truyền đối số cho hàm. Có thể truyền đối số theo giá trị với các kiểu dữ liệu cơ bản (char, short, int, long, long long, float, double và long double) và các cấu trúc(structures). Phương pháp thay thế là truyền một con trỏ tới biến đối số thay vì giá trị của chính biến đó. Phương pháp truyền đối số này được gọi là truyền bằng tham chiếu. Vì hàm có địa chỉ của biến thực tế nên hàm có thể sửa đổi giá trị của biến

Truyền bằng tham chiếu là cách duy nhất để truyền một mảng cho một hàm; không thể truyền một mảng theo giá trị. Tuy nhiên, với các loại dữ liệu khác, bạn có thể sử dụng một trong hai phương pháp. Nếu chương trình của bạn sử dụng các cấu trúc lớn, việc chuyển chúng theo giá trị có thể khiến chương trình của bạn hết dung lượng ngăn xếp. Ngoài điều này ra  việc truyền đối số bằng tham chiếu thay vì theo giá trị mang lại ưu điểm cũng như nhược điểm: 

• Ưu điểm của việc truyền tham chiếu là hàm có thể sửa đổi giá trị của biến đối số. 

• Nhược điểm của việc truyền tham chiếu là hàm có thể sửa đổi giá trị của biến đối số. 

Nếu chương trình của bạn yêu cầu một hàm sửa đổi một biến đối số thì việc truyền theo tham chiếu là một lợi thế. Nếu không có nhu cầu như vậy thì thật bất lợi vì có thể vô tình sửa đổi

```c
x = half(x);
float half(float y)
{
	return y/2;
}
```

Tuy nhiên, hãy nhớ rằng một hàm chỉ có thể trả về một giá trị duy nhất. Bằng cách chuyển một hoặc nhiều đối số theo tham chiếu, bạn cho phép một hàm "trả về" nhiều giá trị cho chương trình gọi. Hình 18.2 minh họa việc truyền tham chiếu cho một đối số

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/26ff25a1-5133-4405-825c-5e7f20a0d379/Untitled.png)

Khi bạn chuyển qua tham chiếu, bạn phải đảm bảo rằng định nghĩa hàm và nguyên mẫu phản ánh thực tế rằng đối số được truyền cho hàm là một con trỏ. Trong phần nội dung của hàm, bạn cũng phải sử dụng toán tử gián tiếp để truy cập (các) biến được truyền bằng tham chiếu. 

Liệt kê 18.1 thể hiện việc truyền theo tham chiếu và truyền theo giá trị mặc định. Kết quả đầu ra của nó cho thấy rõ ràng rằng một biến được truyền theo giá trị thì hàm không thể thay đổi được, trong khi một biến được truyền theo tham chiếu có thể bị thay đổi. Tất nhiên, một hàm không cần sửa đổi một biến được truyền bằng tham chiếu. Trong trường hợp như vậy, không có lý do gì để chuyển qua tham chiếu

```c
/* Passing arguments by value and by reference. */
#include <stdio.h>

void by_value(int a, int b, int c);
void by_ref(int *a, int *b, int *c);

int main(void)
{
    int x = 2, y = 4, z = 6;

    printf("\nBefore calling by_value(), x = %d, y = %d, z = %d.", x, y, z);

    by_value(x, y, z);

    printf("\nAfter calling by_value(), x = %d, y = %d, z = %d.", x, y, z);

    by_ref(&x, &y, &z);

    printf("\nAfter calling by_ref(), x = %d, y = %d, z = %d.\n", x, y, z);

    return 0;
}

void by_value(int a, int b, int c)
{
    a = 0;
    b = 0;
    c = 0;
}

void by_ref(int *a, int *b, int *c)
{
    *a = 0;
    *b = 0;
    *c = 0;
}
```

```c
Before calling by_value(), x = 2, y = 4, z = 6.
After calling by_value(), x = 2, y = 4, z = 6.
After calling by_ref(), x = 0, y = 0, z = 0
```

## **Functions That Return a Pointer**

```c
double *func1(parameter_list);
struct address *func2(parameter_list);
```

dòng đầu trả về pointer dạng double

dòng 2 trả về pointer dạng address

```c
double (*func)(...); /* Pointer to a function that returns a double. */
double *func(...); /* Function that returns a pointer to a double. */
```

```c

```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/5e1409bf-5466-46bc-a3a6-1dfdaf6220c9/Untitled.png)

```c
Enter two integer values: 1111 3000
The larger value is 3000.
The larger value is 3000.
```

# DAY 19: EXPLORING THE C FUNCTION LIBRARY

## thư viện toán học

**math.h**

## Hàm lượng giác

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/d5ddd10b-7d13-47b3-a56d-df8e96a51b31/Untitled.png)

## **Hàm số mũ và hàm logarit**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/042f9a04-f1a1-4fb8-ae2a-f4e31e66880f/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/a33cee7e-0817-4407-b9b7-59638c5e1f57/Untitled.png)

## **Hàm hyperbol**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/b8f68cc3-95b4-4e80-9f6f-48842680b245/Untitled.png)

## **Các hàm toán học khác**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/2ef2a41e-4be9-4f12-8530-56040198684d/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9269fc3-a768-4e73-a071-729d0f5919f2/9683cad4-657e-4cdf-a57f-0634b64c13f3/Untitled.png)

## **Dealing with Time**

**time.h**

### Thể hiện thời gian

```c
struct tm {
int tm_sec; // seconds after the minute - [0,59]
int tm_min; // minutes after the hour - [0,59]
int tm_hour; // hours since midnight - [0,23]
int tm_mday; // day of the month - [1,31]
int tm_mon; // months since January - [0,11]
int tm_year; // years since 1900
int tm_wday; // days since Sunday - [0,6]
int tm_yday; // days since January 1 - [0,365]
int tm_isdst; // daylight savings time flag
};
```

### **The Time Functions**

### Lấy thời gian hiện tại

```c
time_t time(time_t *timeptr);
```

```c
time_t now;
now = time(0);

// or
time_t now;
time_t *ptr_now = &now;
time(ptr_now);

```

**Displaying Times**

**Calculating Time Differences**

```c
double difftime(time_t later, time_t earlier)
```

 hàm clock(), hàm này trả về lượng thời gian đã trôi qua kể từ khi chương trình bắt đầu thực thi, tính bằng đơn vị 1/100 giây.

```c
clock_t clock(void)
```

## **Error-Handling**

### **The assert() Macro**

Macro khẳng định() có thể chẩn đoán lỗi chương trình. **assert.h** 

```c
void assert(int expression);
```

**The errno.h Header File**

Tệp tiêu đề errno.h xác định một số macro được sử dụng để xác định và ghi lại các lỗi thời gian chạy. Các macro này được sử dụng cùng với hàm perror(), được mô tả trong phần tiếp theo

**The perror() Function**

Hàm perror() là một công cụ xử lý lỗi khác của C. Khi được gọi, perror() hiển thị thông báo trên stderr mô tả lỗi gần đây nhất xảy ra trong lệnh gọi hàm thư viện hoặc lệnh gọi hệ thống. 

## **Searching and Sorting**

### **Searching with bsearch()**

### **Sorting with qsort()**

quicksort algorithm

### **Searching and Sorting: Two Demonstrations**

# DAY 20: WORKING WITH MEMORY (chưa xong)

## **Automatic Type Conversions**

Tùy thuộc vào biến nào đứng trước

- Nếu một trong hai toán hạng là long double thì toán hạng còn lại sẽ được thăng cấp thành kiểu long double
- double ⇒ double
- float ⇒ float
- long ⇒ long

tự động định dạng kiểu dữ liệu của biến 

EX: 

Ví dụ: nếu x là int và y là float, 

 biểu thức x/y sẽ cho x thành kiểu float trước khi biểu thức tính toán. 

Điều này không có nghĩa là kiểu dữ liệu biến x bị thay đổi ⇒  một bản sao kiểu float của x được tạo và sử dụng trong việc đánh giá biểu thức.  Tương tự, nếu x là kiểu double và y là kiểu float thì y sẽ được thăng cấp thành double

## **Chuyển đổi rõ ràng bằng cách sử dụng Typecasts**

```c
(float)i;
```

Cách sử dụng phổ biến nhất của Typecassts là tránh mất phần phân số của câu trả lời trong phép chia số nguyên

EX:

```c
#include <stdio.h>

int main(void) {
    int i1 = 100, i2 = 40;
    float f1;

    f1 = (float)i1 / i2;
    printf("%lf\n", f1);

    return 0;
}
```

```c
2.000000
```

Đáp án là 2.00000, nhưng 100/40 = 2.5

Biểu thức i1/i2 ở dòng 8 chứa hai biến kiểu int. . Điều này là do hai toán hạng đều có kiểu int. Như vậy, kết quả chỉ có thể biểu thị số nguyên nên phần phân số của đáp án sẽ bị mất. 

việc gán kết quả của i1/i2 cho một biến kiểu float sẽ biến  nó thành kiểu float. ⇒ Nhưng muộn rồi cưng 

Để tránh loại thiếu chính xác này, bạn phải ép kiểu một trong các biến kiểu int thành kiểu float. 

```c
f1 = (float)i1/i2;
```

### 

## **Allocating Memory Storage Space**

Thư viện C chứa các hàm phân bổ không gian lưu trữ bộ nhớ trong thời gian chạy, một quá trình được gọi là cấp phát bộ nhớ động (**dynamic memory allocation**). Kỹ thuật này có thể có những lợi thế đáng kể so với việc phân bổ bộ nhớ rõ ràng trong mã nguồn chương trình bằng cách khai báo các biến, cấu trúc và mảng. 

Phương pháp sau này, được gọi là cấp phát bộ nhớ tĩnh (tatic memory allocation), yêu cầu bạn biết chính xác lượng bộ nhớ bạn cần khi viết chương trình. Việc cấp phát bộ nhớ động cho phép chương trình phản ứng, trong khi đang thực thi, theo yêu cầu về bộ nhớ, chẳng hạn như thông tin đầu vào của người dùng. Tất cả các chức năng xử lý cấp phát bộ nhớ động đều yêu cầu tệp tiêu đề stdlib.h; với một số trình biên dịch, malloc.h cũng được yêu cầu. Lưu ý rằng tất cả các hàm phân bổ đều trả về một con trỏ kiểu void. Như bạn đã học ở Ngày 18, một con trỏ kiểu void phải được chuyển sang kiểu thích hợp trước khi được sử dụng

## **ALLOCATING MEMORY WITH THE MALOC() FUNCTION**

⇒ Phân bố không gian cho chuỗi. Ko giới hạn khi phân bố cho chuỗi, 

```c
void *malloc(size_t num);
```

w
