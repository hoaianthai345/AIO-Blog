---
title: NoSQL
---

Date: 03/07/2025
Day/Week: Module 2, Thu, Week1
Status: Not started
Tag: AIO

# I. Introduction to NoSQL

## 1. What is Database

Cơ sở dữ liệu (database) là khái niệm rất phổ biến trong ngành công nghệ, nhưng nếu bạn mới bắt đầu, hãy bắt đầu từ những điều đơn giản nhất: **dữ liệu là gì, và tại sao phải tổ chức nó lại thành cơ sở dữ liệu?**

Hãy tưởng tượng bạn có một tờ giấy ghi:

> Tên: Thái Hoài An
> Tuổi: 20
> Hình ảnh: ….

Đó chính là **dữ liệu** – thông tin đơn lẻ về một cá nhân. Nó có thể tồn tại ở nhiều dạng: con số, văn bản, ảnh, âm thanh hay thậm chí cả video. Nhưng nếu bạn có hàng ngàn tờ như vậy – thông tin của hàng ngàn người – thì chắc chắn bạn sẽ cần một cách **quản lý có tổ chức** để tra cứu, cập nhật, phân loại nhanh chóng. Đó là lý do **database** ra đời.

Một **database** về bản chất là tập hợp có tổ chức của các dữ liệu. Nó giống như một thư viện thông minh – nơi bạn không chỉ lưu sách, mà còn có hệ thống để tìm sách nhanh, phân loại sách chính xác và đảm bảo sách không bị thất lạc. Trong thế giới số, database giúp ứng dụng của bạn chạy mượt mà, lưu giữ thông tin người dùng, sản phẩm, giao dịch và hàng triệu thứ khác.

## 2. Thành phần cấu tạo database

Khi bạn xây dựng một ứng dụng cần lưu trữ dữ liệu, bạn sẽ cần nhiều hơn là chỉ nhét dữ liệu vào đâu đó. Một hệ thống cơ sở dữ liệu đúng nghĩa thường gồm 5 thành phần phối hợp với nhau:

| Thành phần | Vai trò chính |
| --- | --- |
| **Hardware** | Phần cứng – nơi dữ liệu được lưu trữ và xử lý (server, SSD…) |
| **Software** | Hệ điều hành và chương trình quản lý dữ liệu (ví dụ: MySQL, MongoDB) |
| **Data** | Thông tin được lưu trữ – chính là “linh hồn” của database |
| **Procedures** | Quy trình – hướng dẫn người dùng cách thao tác với database |
| **Access Language** | Ngôn ngữ truy vấn (ví dụ: SQL hoặc MQL trong MongoDB) giúp tương tác với dữ liệu |

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image.png)

Vậy nên, database là một hệ sinh thái chứ không chỉ là chỗ chứa. Nó vừa có phần cứng mạnh mẽ, phần mềm điều khiển, quy trình thao tác chuẩn hóa và một ngôn ngữ để tương tác.

## 3. DBMS

Cho đến lúc này, ta đã biết database là nơi lưu trữ thông tin có tổ chức. Nhưng ai sẽ là người điều khiển mọi thứ bên trong nó? Đó chính là vai trò của **DBMS – Database Management System**.

DBMS là một phần mềm trung gian giữa người dùng (hoặc ứng dụng) và nơi lưu trữ dữ liệu. Nó giống như người quản lý thư viện – bạn không cần tự mình đi lục tung từng kệ sách, mà chỉ cần yêu cầu, và người quản lý sẽ lấy đúng sách cho bạn. Không chỉ vậy, DBMS còn chịu trách nhiệm **định nghĩa**, **ghi nhận**, **truy vấn**, **cập nhật** và **quản lý toàn bộ dữ liệu**.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%201.png)

Trong sơ đồ ở trên, bạn có thể thấy:

- Người dùng hoặc ứng dụng gửi yêu cầu đến DBMS, chẳng hạn như: “Tìm danh sách sinh viên trên 18 tuổi”.
- DBMS tiếp nhận, hiểu, rồi đi vào khu vực lưu trữ dữ liệu (Storage Area) để lấy kết quả phù hợp.
- Cơ sở dữ liệu bên dưới có thể thuộc nhiều kiểu: **quan hệ (Relational)**, **cây phân cấp (Hierarchical)**, **tệp phẳng (Flat files)** hoặc **đối tượng (Object-Oriented)**.

Việc sử dụng DBMS giúp hệ thống trở nên chuyên nghiệp và có khả năng mở rộng dễ dàng. Bạn có thể tưởng tượng nếu không có DBMS, mỗi khi cần truy cập dữ liệu, bạn sẽ phải viết lại toàn bộ logic xử lý từ đầu – giống như xây dựng lại thư viện mỗi lần muốn mượn sách.

**Một số DBMS phổ biến:**

- **SQL-based**: MySQL, PostgreSQL, Oracle
- **NoSQL-based**: MongoDB, Cassandra, Firebase

---

> 📌 DBMS là phần mềm, còn database là tập dữ liệu được phần mềm đó quản lý. Đừng nhầm lẫn hai khái niệm này!
> 

## 4. SQL Database

Trước khi nói đến NoSQL, bạn cần hiểu rõ SQL đang làm gì, và làm tốt như thế nào.

SQL (Structured Query Language) là ngôn ngữ truy vấn tiêu chuẩn để làm việc với **cơ sở dữ liệu quan hệ (Relational Database)**. Trong kiểu cơ sở dữ liệu này, thông tin được lưu trữ trong các bảng – giống như bảng tính Excel, với hàng và cột. Mỗi bảng là một **thực thể**, như: bảng sinh viên, bảng môn học, bảng điểm...

Ví dụ đơn giản thế này:

- Bảng **Student** chứa thông tin sinh viên: ID và tên.
- Bảng **Subject** chứa danh sách môn học.
- Bảng **Mark** chứa điểm số, và liên kết với 2 bảng trên bằng khóa ngoại (`studentID`, `subjectID`).

Đây gọi là **mô hình quan hệ** – vì các bảng không tồn tại riêng lẻ mà được **liên kết với nhau bằng các mối quan hệ**. Khi bạn muốn biết “Thái học môn nào và điểm bao nhiêu?”, hệ thống sẽ phải:

1. Truy tìm `studentID` của Thái,
2. Dò theo bảng điểm để tìm các dòng có cùng `studentID`,
3. Kết nối sang bảng môn học để lấy `subjectName`.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%202.png)

Hệ quản trị như MySQL hay PostgreSQL sẽ dùng SQL để xử lý các truy vấn như vậy. SQL rất mạnh mẽ trong việc đảm bảo tính toàn vẹn dữ liệu, tránh trùng lặp, và phù hợp với các hệ thống nghiệp vụ có cấu trúc rõ ràng (như ngân hàng, quản lý nhân sự, kế toán...).

**Nhưng điều gì xảy ra khi:**

- Dữ liệu thay đổi cấu trúc liên tục?
- Hệ thống có hàng triệu request mỗi giây?
- Không chỉ lưu văn bản mà còn cả hình ảnh, đoạn chat, logs?

SQL bắt đầu bộc lộ giới hạn. Đó là lúc NoSQL xuất hiện.

## 5. NoSQL Database

Thật ra, SQL từng là lựa chọn số một cho mọi hệ thống – nhưng **khi thế giới chuyển mình sang kỷ nguyên dữ liệu lớn (Big Data)**, mạng xã hội, IoT, video streaming… thì SQL bắt đầu “đuối sức”. Lý do nằm ở chỗ: không phải mọi loại dữ liệu đều phù hợp với dạng bảng truyền thống. Không phải lúc nào bạn cũng biết trước cột nào sẽ cần, quan hệ nào sẽ phát sinh.

Và đó là lúc **NoSQL** xuất hiện.

**NoSQL nghĩa là gì?**

Tên gọi **NoSQL** không có nghĩa là "không dùng SQL", mà là:

- **Not Only SQL**: không chỉ giới hạn ở SQL
- **No Relational**: không dựa trên quan hệ giữa bảng
- **No RDBMS**: không cần hệ quản trị kiểu quan hệ

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%203.png)

## 6. NoSQL Database Types?

Thay vì chia thành nhiều bảng rời rạc và kết nối qua khóa ngoại, NoSQL chọn cách **lưu toàn bộ thông tin liên quan vào trong một cấu trúc duy nhất**, thường là dạng JSON hoặc tương tự. Ví dụ:

```json
{
  "studentID": 1,
  "studentName": "Anh"
}
```

So với bảng kiểu SQL:

| studentID | studentName |
| --- | --- |
| 1 | Anh |

... thì cách này **mềm dẻo hơn nhiều**: bạn có thể thêm bất kỳ trường nào mà không cần định nghĩa trước như `email`, `địa chỉ`, hay `sở thích`. Mỗi "bản ghi" trong NoSQL có thể có cấu trúc riêng, không bị ràng buộc chặt chẽ.

Dưới đây là 3 cách lưu trữ dữ liệu NoSQL phổ biến nhất:

### KEY-VALUE STORE DATABASE

Đây là dạng đơn giản nhất: mỗi bản ghi là một cặp **khóa** và **giá trị**. Khóa là định danh duy nhất (giống như tên), còn giá trị là dữ liệu đi kèm. Ví dụ:

```json
"user123": {
  "name": "Thái",
  "age": 20
}
```

Hệ thống như Redis dùng mô hình này để lưu cache cực nhanh – lý tưởng cho những thao tác đọc-ghi tốc độ cao, đơn giản.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%204.png)

> **Cache** (phát âm giống "két") là một vùng nhớ tạm, dùng để **lưu lại những dữ liệu được truy cập thường xuyên**, để lần sau khi cần thì lấy ra nhanh hơn, **không phải truy xuất lại từ đầu**.
> 
> 
> Ví dụ đơn giản:
> 
> - Khi bạn truy cập một trang sản phẩm trên Shopee, hệ thống phải tải tên, giá, đánh giá, ảnh… Nếu mỗi lần bạn quay lại trang này mà hệ thống đều truy vấn database lại từ đầu, thì sẽ tốn thời gian và tài nguyên.
> - Vì vậy, hệ thống sẽ **cache** lại thông tin sản phẩm đó trong RAM. Lần sau chỉ cần lấy nhanh từ cache → tiết kiệm cả triệu lần truy vấn giống nhau mỗi ngày.
> 
> **Redis** (REmote DIctionary Server) là **một hệ thống lưu trữ dữ liệu dạng key-value trong bộ nhớ RAM**, nổi tiếng với tốc độ cực nhanh. Nó thường được dùng để:
> 
> - Làm **cache trung gian** cho backend
> - Lưu **session người dùng**
> - Xử lý **queue** và **thống kê realtime**
> - Lưu **token tạm thời** trong các hệ thống xác thực
> 
> Khác với database truyền thống (lưu trên ổ cứng), Redis ưu tiên tốc độ và thường dùng cho **dữ liệu ngắn hạn**. Dù vậy, nó vẫn có thể lưu trữ bền nếu cần.
> 

### Graph database

Một dạng đặc biệt trong thế giới NoSQL chính là **Graph Database** - nơi mọi thứ được lưu dưới dạng **nút (node)** và **liên kết (edge)**. Thay vì chỉ lưu ai biết ai, Graph DB còn lưu được **mối quan hệ là gì**, **tính chất mối quan hệ ra sao**, và cả **thuộc tính của mối quan hệ**.

**Ví dụ** 

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%205.png)

Giả sử bạn có 3 thực thể:

- **Anh** và **Thái** là hai người dùng
- **Thái** thích **AI**
- **Thái** sống tại **Nghệ An**

Nếu bạn lưu bằng bảng (SQL), bạn phải tạo ra ít nhất 3 bảng:

- Bảng user
- Bảng sở thích
- Bảng địa lý
    
    Rồi liên kết khóa ngoại rất phức tạp.
    

Nhưng với **Graph Database**, bạn chỉ cần dựng đồ thị:

- Mỗi người, chủ đề, địa điểm là một **node**
- Mỗi mối liên hệ như “Is_Friend_With”, “Like”, “Located_In” là **edge**
- Mọi thứ có thể đi kèm thuộc tính: thời gian, mức độ thân thiết, số lượt tương tác...

**Khi nào nên dùng Graph DB?**

- Mạng xã hội (ai tương tác với ai)
- Gợi ý kết nối ("người này có thể bạn quen")
- Hệ thống khuyến nghị (Netflix, Spotify)
- Phát hiện gian lận (phân tích chuỗi giao dịch bất thường)

Một số công cụ phổ biến là **Neo4j**, **ArangoDB**, **Amazon Neptune**. **Bảng xếp hạng các hệ quản trị Graph Database** :

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/6e86df0e-c284-4eb0-b021-cfe44131afa9.png)

Source [https://db-engines.com/en/ranking/graph+dbms](https://db-engines.com/en/ranking/graph+dbms)

Graph DB không hề phổ biến như Document DB (MongoDB), nhưng khi bài toán cần đến **quan hệ đa chiều và truy vấn theo kết nối**, nó là vũ khí cực mạnh. Thay vì JOIN 4-5 bảng như SQL, Graph DB chỉ cần đi qua 3 nút là xong.

### DOCUMENT DATABASE

**Document Database** là loại được sử dụng phổ biến nhất — đặc biệt là trong các ứng dụng web hiện đại. Đây là dữ liệu dạng JSON đã được đề cập ở trên.

**Ví dụ:**

```python
{
  "_id": "tomjohnson",
  "firstName": "Tom",
  "lastName": "Johnson",
  "email": "tom.johnson@digitalocean.com",
  "department": ["Finance", "Accounting"],
  "socialMediaAccounts": [
    { "type": "facebook", "username": "tom.fb" },
    { "type": "twitter", "username": "@tomjohnson" }
  ]
}
```

Tài liệu trên chứa đủ thông tin của một người dùng: tên, email, bộ phận, mạng xã hội – mà không cần chia ra 3 bảng như SQL. Mỗi document có thể có cấu trúc hơi khác nhau mà không lỗi – đó là sức mạnh của document database: **linh hoạt, dễ mở rộng**.

**Các định dạng phổ biến: JSON, BSON, XML**

- **JSON** là chuẩn dễ đọc, rất phổ biến trong web.
- **BSON** là phiên bản nhị phân tối ưu của JSON, dùng trong MongoDB.
- **XML** cũng được dùng để biểu diễn cấu trúc, đặc biệt trong các ứng dụng như **gán nhãn dữ liệu hình ảnh (image annotation)**.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%206.png)

Trong các dự án AI, dữ liệu được lưu dưới dạng ảnh + file XML mô tả vùng chứa đối tượng. Đây là minh chứng sống động cho việc document không cần "chia cột" — mỗi tệp là một đơn vị độc lập.

**Bảng xếp hạng các hệ quản trị Documents Database** :

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%207.png)

Source: [https://db-engines.com/en/ranking/document+store](https://db-engines.com/en/ranking/document+store)

# II. Introduction to MongoDB

Nếu bạn từng viết API cho website, ứng dụng học tập, thương mại điện tử hay hệ thống quản lý người dùng, khả năng cao bạn đã nghe đến **MongoDB**. Vậy MongoDB là gì và tại sao nó được ưa chuộng đến vậy?

## 1. MongoDB

**MongoDB là một document database** – tức là nó lưu dữ liệu dưới dạng các "tài liệu" có cấu trúc giống JSON.

Thay vì chia nhỏ thông tin thành nhiều bảng như trong SQL, MongoDB cho phép bạn gói gọn toàn bộ dữ liệu của một thực thể (ví dụ: người dùng, sản phẩm, bài viết…) vào một "document" duy nhất, rồi lưu nó vào một nhóm gọi là **collection**.

> Nói cách khác:
> 
> - **Database** là cái tủ đựng hồ sơ
> - **Collection** là ngăn kéo chứa từng loại hồ sơ
> - **Document** là từng tờ hồ sơ chi tiết

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%208.png)

## 2. Documents in MongoDB

### Sử dụng định dạng JSON (Java Script Object Notation)

```json
{
  "_id": 1,
  "name": "Thai",
  "age": 20,
  "mark": 3.0,
  "like": "music"
}
```

Ở đây:

- `_id`: là **mã định danh duy nhất** cho mỗi document
- Các cặp `key: value` chính là các trường dữ liệu

### MongoDB hỗ trợ nhiều kiểu dữ liệu

Các field trong MongoDB có thể chứa nhiều loại dữ liệu khác nhau:

- **Numerical**: số nguyên, số thực
- **String**: chuỗi ký tự
- **Date**: ngày giờ
- **Array, Object (nested document)**

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%209.png)

**Ví dụ:**

```json
{
  "name": "Thai",
  "dateOfBirth": "1997-07-10",
  "phone": ["0123", "1235"]
}
```

### MongoDB cực kỳ linh hoạt

Khác với SQL bắt buộc mọi dòng phải giống nhau, MongoDB cho phép các document trong cùng một collection **không cần giống nhau** về cấu trúc. Bạn có thể thêm hoặc bỏ trường tùy ý.

```json
// Document 1
{
  "name": "Thai",
  "age": 20,
  "like": "music"
}

// Document 2
{
  "name": "Thai",
  "age": 20,
  "like": "music",
  "phone": "01234"
}
```

Chúng cùng thuộc một collection, nhưng rõ ràng khác nhau.

### Nested Document: Document trong document

Bạn có thể *nhúng* một document khác vào trong document cha. Kiểu như lưu thông tin địa chỉ bên trong thông tin người dùng:

```json
{
  "name": "Thai",
  "address": {
    "city": "Ha Noi",
    "postcode": "100"
  }
}
```

Đây là một điểm cực mạnh của MongoDB – thay vì tách bảng như trong SQL, bạn có thể nhúng dữ liệu trực tiếp để tăng hiệu suất đọc và đơn giản hóa cấu trúc.

### Array: Lưu nhiều giá trị trong một trường

MongoDB hỗ trợ kiểu **mảng (array)**, cho phép bạn lưu nhiều giá trị trong một field.

Ví dụ: số điện thoại của người dùng:

```json
{
  "name": "Thai",
  "phone": ["0123", "1235"]
}
```

Điều này giúp bạn dễ dàng thao tác với các trường có nhiều phần tử mà không cần tạo bảng phụ như trong SQL.

### Documents are polymorphic

Bạn có thể tưởng tượng mỗi document như một **hồ sơ cá nhân**, và MongoDB giống như một chiếc hộp linh hoạt – thêm gì cũng được, bỏ gì cũng được, chỉ cần bạn biết cách truy cập lại.

## 3. MongoDB Ecosystem

MongoDB là một **hệ sinh thái** gồm nhiều phiên bản, công cụ và tiện ích hỗ trợ để quản lý dữ liệu linh hoạt chứ không phải một cơ sở dữ liệu đơn lẻ, tương tự như MySQL hay PostgreSQL.

### Ba phiên bản của MongoDB

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2010.png)

- **Community Edition** là lựa chọn phổ biến nhất cho sinh viên, developer cá nhân, hoặc các startup nhỏ. Nó miễn phí, mã nguồn mở và đầy đủ tính năng cốt lõi. Nếu bạn đang học MongoDB hoặc làm side project, đây là lựa chọn tối ưu.
- **Enterprise Edition** được thiết kế cho doanh nghiệp lớn. Phiên bản này bổ sung nhiều tính năng như bảo mật nâng cao, audit log, tích hợp LDAP, cũng như hỗ trợ kỹ thuật chuyên sâu từ MongoDB Inc.
- **MongoDB Atlas** là nền tảng đám mây của MongoDB. Bạn không cần cài đặt hay cấu hình gì phức tạp – chỉ cần đăng ký tài khoản, tạo cluster, và bắt đầu thao tác dữ liệu ngay. Atlas hỗ trợ auto-scaling, backup định kỳ, và phân vùng toàn cầu (global distribution).

### Bộ công cụ hỗ trợ

- **Mongo Shell** là giao diện dòng lệnh cho phép bạn chạy truy vấn trực tiếp. Nó tương tự như terminal cho MongoDB – cực kỳ mạnh mẽ khi bạn đã quen cú pháp.
- **MongoDB Drivers** giúp bạn kết nối và thao tác MongoDB từ ngôn ngữ lập trình yêu thích như Python, Java, Node.js… Nếu bạn đang dùng Flask, Express hoặc Spring Boot, bạn sẽ cần những driver này.
- **BI Connectors** là cầu nối giữa MongoDB và các công cụ phân tích như Tableau hoặc Power BI. Dữ liệu Mongo dạng document có thể được ánh xạ thành bảng (relational view) để phân tích trực quan.
- **Compass** là GUI chính thức của MongoDB – một giao diện đồ họa giúp bạn quản lý dữ liệu mà không cần viết lệnh. Bạn có thể xem collection, chỉnh sửa document, tạo index, vẽ biểu đồ query performance… mà không cần biết Mongo Shell.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2011.png)

# III. Installation

Bạn muốn bắt đầu học MongoDB nhưng không muốn cài đặt gì phức tạp trên máy? Vậy thì **MongoDB Atlas** chính là giải pháp lý tưởng – một nền tảng cloud hoàn toàn miễn phí, cho phép bạn tạo cluster chỉ trong vài cú click.

> **Cluster** trong MongoDB là một nhóm gồm **một hoặc nhiều server** (gọi là *node*) hoạt động cùng nhau để:
> 
> - Lưu trữ dữ liệu MongoDB
> - Đảm bảo tính sẵn sàng (availability)
> - Mở rộng hiệu suất (scalability)
> - Và chịu lỗi (fault-tolerance)
> 
> Nói đơn giản, cluster = tập hợp các server chạy MongoDB làm việc phối hợp như một hệ thống duy nhất.
> 

## 1. Mongo Atlas

Đây là phần hướng dẫn cách tạo **tài khoản Atlas** và **cluster miễn phí** để bạn có thể thực hành MongoDB ngay.

### Bước 1 – Tạo tài khoản MongoDB Atlas

Bạn có thể truy cập trang [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) và đăng ký tài khoản hoàn toàn miễn phí. Chỉ cần email, không cần thẻ tín dụng. Sau khi đăng ký, bạn sẽ được đưa vào trang dashboard để bắt đầu tạo cơ sở dữ liệu.

> Tip: Bạn có thể đăng ký bằng GitHub hoặc Google để tiết kiệm thời gian.
> 

### **Bước 2 – Tạo một cluster miễn phí**

Sau khi đăng nhập, hãy chọn "Build a Database" và đảm bảo bạn chọn tab **Free** (như hình).

Bạn sẽ cần cấu hình vài thông tin cơ bản:

- **Cloud Provider & Region:** Nên chọn một region gần bạn nhất, ví dụ: `AWS - Hong Kong (ap-east-1)`để giảm độ trễ.
- **Cluster Capacity:** Với gói free tier, bạn sẽ nhận được khoảng `0 - 100 Ops/Sec` và `512MB Storage`, đủ cho học tập và dự án nhỏ.
- **Additional Settings:** Mặc định là `MongoDB 8.0`, chưa có backup – phù hợp với nhu cầu sandbox học tập.
- **Cluster Name:** Đặt tên dễ nhớ, ví dụ `Cluster0`.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2012.png)

Nhấn **Create Cluster**, và chỉ sau vài phút là bạn đã có một MongoDB cloud sẵn sàng kết nối.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2013.png)

### **Bước 3 – Tạo người dùng Database mới**

Sau khi bạn đã tạo cluster và thiết lập IP cho phép truy cập, bước tiếp theo là tạo một **người dùng database** – hay còn gọi là **database user**.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2014.png)

Bạn sẽ thấy form gồm:

- **Username**: tên tài khoản dùng để đăng nhập
- **Password**: mật khẩu tương ứng (có thể tự tạo hoặc để hệ thống sinh ngẫu nhiên)
- **Database Access**: mặc định thường là `admin`
- **User Privileges**: chọn quyền phù hợp, ví dụ:
    - **Read and write to any database**
    - **Atlas admin**
    - Hoặc custom (tuỳ chỉnh theo từng database)

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2015.png)

> Giả sử bạn đang xây dựng một ứng dụng quản lý sách, bạn có thể tạo:
> 
- `bookReader`: chỉ có quyền **read** dữ liệu trong database `library`
- `bookManager`: có quyền **read/write** dữ liệu

### Bước 4. Cấp quyền IP truy cập (Add New IP Access)

MongoDB Atlas **không cho phép bất kỳ ai trên Internet truy cập vào database của bạn một cách tự do**. Mỗi địa chỉ IP (hoặc dải IP) đều phải được **cấu hình rõ ràng trong danh sách cho phép (Access List)** thì mới có thể kết nối tới cluster.

Điều này giống như bạn đang xây tường bao quanh cơ sở dữ liệu của mình – chỉ mở cửa **cho những địa chỉ đáng tin cậy**.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2016.png)

**Có 3 lựa chọn chính khi thêm IP:**

| Loại IP | Ý nghĩa |
| --- | --- |
| Your current IP | Tự động phát hiện IP bạn đang dùng (thường dùng trong giai đoạn setup) |
| Allow access from anywhere (0.0.0.0/0) | Cho phép tất cả các IP truy cập – **KHÔNG AN TOÀN**, chỉ dùng để test |
| Add manually | Bạn nhập IP cụ thể hoặc dải IP cần cho phép (ví dụ: `123.45.67.0/24`) |

## 2. MongoDB Shell and Database Tools

### **MongoDB Shell (mongosh)** – Giao diện dòng lệnh thông minh

- Là môi trường CLI để bạn **gõ lệnh truy vấn trực tiếp đến database**.
- Hỗ trợ cú pháp **JavaScript** – ví dụ:

```jsx
db.users.find({ age: { $gte: 18 } })
```

- Phù hợp cho:
    - Kiểm tra dữ liệu nhanh
    - Chạy script thao tác database
    - Test truy vấn trước khi viết code

Bạn có thể cài mongosh riêng hoặc dùng sẵn trong MongoDB Compass.

### **MongoDB Compass** – Giao diện đồ họa cho người không thích terminal

- Xem cấu trúc database trực quan
- Chạy truy vấn dạng GUI hoặc code
- Thống kê hiệu suất, chỉ số index, validation schema

Rất phù hợp cho người mới bắt đầu hoặc khi cần trình bày dữ liệu trực quan.

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2017.png)

### **MongoDB Drivers** – Kết nối database từ ứng dụng

- MongoDB hỗ trợ đa ngôn ngữ: **Node.js, Java, Python, C#, PHP,…**
- Cho phép bạn **gửi truy vấn từ app đến database** một cách an toàn và hiệu quả
- Ví dụ (Node.js – mongoose):

```jsx
const mongoose = require("mongoose");
mongoose.connect("mongodb+srv://username:password@cluster.mongodb.net/myDB");
```

### **Database Tools** – Bộ công cụ quản trị (CLI)

| Công cụ | Mục đích chính |
| --- | --- |
| `mongodump` | Sao lưu dữ liệu database → file `.bson` |
| `mongorestore` | Khôi phục dữ liệu từ file backup |
| `mongoimport` | Import dữ liệu từ `.json`, `.csv` |
| `mongoexport` | Export dữ liệu từ MongoDB → `.json`, `.csv` |

Dùng để **di chuyển dữ liệu giữa các môi trường (local → production)** hoặc sao lưu định kỳ.

# IV. Mongo Query Language

## 1. Tạo / Xóa Database và Collection

MongoDB không sử dụng cú pháp SQL cổ điển như `CREATE TABLE`, `DROP TABLE`, mà thay vào đó là **MQL – Mongo Query Language** với phong cách gần gũi JavaScript. Ta có thể thao tác bằng:

- **MongoDB Atlas UI**: trực quan, dễ dùng
- **MongoDB Compass**: giao diện ứng dụng desktop
- **Mongo Shell**: công cụ CLI dành cho coder chính hiệu

**Xem danh sách các database:**

```bash
show dbs
```

**Tạo mới hoặc chuyển sang database có sẵn:**

```bash
use myDatabase
```

> Nếu myDatabase chưa tồn tại, nó sẽ được tạo ngầm khi bạn insert dữ liệu đầu tiên.
> 

**Xóa toàn bộ database hiện tại:**

```bash
db.dropDatabase()
```

**Xem danh sách collection trong database hiện tại:**

```bash
show collections
```

**Tạo collection mới:**

```bash
db.createCollection('students')
```

**Xóa collection:**

```bash
db.students.drop()
```

## 2. Chèn dữ liệu (Insert Document)

Sau khi đã tạo xong một database và collection, bước tiếp theo chính là **chèn dữ liệu** vào. Trong MongoDB, dữ liệu được lưu dưới dạng **document** – tương đương với một object trong JavaScript, hoặc một bản ghi trong RDBMS truyền thống.

Cú pháp để chèn một document:

```jsx
db.collection_name.insert(<document hoặc mảng document>)
```

**Ví dụ 1: Thêm một document vào collection `student`**

```jsx
db.student.insert({ "name": "Thai" })
```

Kết quả sau khi insert:

```jsx
[
  { _id: ObjectId("..."), name: 'Thai' }
]
```

MongoDB sẽ tự động sinh ra `_id` nếu bạn không cung cấp.

**Ví dụ 2: Thêm nhiều documents cùng lúc**

```jsx
db.student.insert([
  { "name": "Thai" },
  { "age": 20 }
])
```

Sau khi thực hiện, collection sẽ có ba document:

```jsx
[
  { _id: ..., name: 'Thai' },
  { _id: ..., name: 'Thai' },
  { _id: ..., age: 20 }
]
```

> Lưu ý: Nếu bạn thêm nhiều document cùng lúc, MongoDB vẫn sẽ đảm bảo mỗi document có một `_id` duy nhất.
> 

## 3. `mongoimport` và `mongoexport` – Làm việc với dữ liệu bên ngoài MongoDB

### mongoimport – Nhập dữ liệu từ file JSON vào MongoDB

Bạn có một file JSON (ví dụ: `companies.json`) và muốn **đưa dữ liệu này vào MongoDB**, bạn sẽ dùng lệnh `mongoimport`.

```bash
mongoimport --uri="<connection_string>" --collection=<collection_name> --file=<file_name>
```

Ví dụ:

```bash
mongoimport \
  --uri="mongodb+srv://user:<password>@cluster0.4zaldul.mongodb.net/sample" \
  --collection=companies \
  --file=companies.json

```

- `-uri`: địa chỉ kết nối đến database MongoDB Atlas
- `-collection`: tên bộ sưu tập sẽ nhập vào
- `-file`: file JSON chứa dữ liệu

### mongoexport – Xuất dữ liệu từ MongoDB ra file JSON

Ngược lại với `mongoimport`, `mongoexport` dùng để **xuất dữ liệu từ một collection ra file JSON**.

```bash
mongoexport --uri="<connection_string>" --collection=<collection_name> --out=<output_file>

```

**Ví dụ:**

```bash
mongoexport \
  --uri="mongodb+srv://user:<password>@cluster0.4zaldul.mongodb.net/test_db" \
  --collection=student \
  --out=student.json
```

- `-collection`: tên bộ sưu tập cần xuất
- `-out`: tên file đầu ra (được tạo từ dữ liệu collection)

## 4. Truy vấn dữ liệu với `findOne()` trong MongoDB

Dùng để **tìm và trả về một document đầu tiên** thỏa mãn điều kiện từ một collection trong MongoDB.

```jsx
db.collection_name.find(query, projection)
```

- `query`: điều kiện lọc (giống WHERE trong SQL)
- `projection`: chọn trường nào cần lấy ra (tuỳ chọn)

**Ví dụ**

```jsx
db.student.find()
```

→ Trả về document đầu tiên trong collection `student`.

```jsx
db.student.find(
  { "name": "Anh" }
)
```

→ Trả về document đầu tiên có trường `name` là `"Anh"`.

```jsx
db.student.find(
	{"name":"Anh", 
	 "age":20}
)
```

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2018.png)

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2019.png)

## 5. Comparison Operators trong MongoDB

MongoDB sử dụng **các toán tử so sánh** (comparison operators) trong cú pháp truy vấn để lọc document theo điều kiện. Mỗi toán tử đều bắt đầu bằng dấu `$`.

```jsx
{ field: { operator: value } }
```

**Ví dụ:**

### Toán tử `$lt` – **Less than** (Nhỏ hơn)

```jsx
db.student.find(
  { "salary": { $lt: 50000 } }
)
```

→ Truy vấn các sinh viên có lương < 50,000.

### Toán tử `$eq` – **Equal to** (Bằng)

```jsx
db.student.find(
  { "salary": { $eq: 50000 } }
)
```

→ Truy vấn các sinh viên có lương = 50,000.

### Danh sách toán tử so sánh thường dùng

| Toán tử | Ý nghĩa | Ví dụ sử dụng |
| --- | --- | --- |
| `$eq` | Bằng | `{ salary: { $eq: 50000 } }` |
| `$ne` | Không bằng | `{ salary: { $ne: 50000 } }` |
| `$gt` | Lớn hơn | `{ salary: { $gt: 50000 } }` |
| `$gte` | Lớn hơn hoặc bằng | `{ salary: { $gte: 50000 } }` |
| `$lt` | Nhỏ hơn | `{ salary: { $lt: 50000 } }` |
| `$lte` | Nhỏ hơn hoặc bằng | `{ salary: { $lte: 50000 } }` |
| `$in` | Nằm trong một tập giá trị | `{ salary: { $in: [40000, 50000, 60000] } }` |
| `$nin` | Không nằm trong một tập giá trị | `{ salary: { $nin: [30000, 35000] } }` |

**Ví dụ:**

Tìm sinh viên có lương **bằng** 50,000:

```
db.student.find({ salary: { $eq: 50000 } })
```

Tìm sinh viên có lương **lớn hơn hoặc bằng** 60,000:

```
db.student.find({ salary: { $gte: 60000 } })
```

Tìm sinh viên có lương **thuộc** nhóm 40k, 50k, 60k:

```
db.student.find({ salary: { $in: [40000, 50000, 60000] } })
```

## 6. Logical Operators trong MongoDB

Khi truy vấn dữ liệu, đôi lúc bạn không chỉ muốn lọc theo **một điều kiện**, mà muốn kiểm tra **nhiều điều kiện cùng lúc**. Lúc đó, **toán tử logic (logical operators)** trong MongoDB sẽ là công cụ đắc lực.

MongoDB hỗ trợ 4 toán tử logic chính:

### `$and`: Tất cả điều kiện đều đúng

**Ý nghĩa**: Trả về các document **thoả tất cả** điều kiện.

```
db.student.find({
  $and: [
    { age: { $gte: 20 } },
    { gpa: { $gt: 3.0 } }
  ]
})
```

**→ Ví dụ thực tế**: Tìm sinh viên từ 20 tuổi trở lên **và** GPA trên 3.0.

### `$or`: Chỉ cần một điều kiện đúng

**Ý nghĩa**: Trả về các document **thoả ít nhất một** điều kiện.

```
db.student.find({
  $or: [
    { city: "Hanoi" },
    { city: "Saigon" }
  ]
})
```

**→ Ví dụ thực tế**: Tìm sinh viên **ở Hà Nội hoặc Sài Gòn**.

### `$not`: Phủ định một điều kiện

**Ý nghĩa**: Trả về các document **không thoả** điều kiện.

```
db.student.find({
  age: { $not: { $lt: 18 } }
})
```

**→ Ví dụ thực tế**: Tìm sinh viên **không nhỏ hơn 18 tuổi**.

### `$nor`: Phủ định toàn bộ

**Ý nghĩa**: Trả về các document **không thoả bất kỳ điều kiện nào**.

```
db.student.find({
  $nor: [
    { major: "Math" },
    { gpa: { $lt: 2.5 } }
  ]
})
```

**→ Ví dụ thực tế**: Tìm sinh viên **không học ngành Toán và GPA không dưới 2.5**.

## 7. Làm quen với `$expr`: Khi bạn cần so sánh phức tạp hơn trong MongoDB

Ở MongoDB, bạn đã quen với cách viết truy vấn như:

```jsx
db.trips.find({ "tripduration": { $gt: 400 } })
```

Câu truy vấn trên đơn giản, đúng nghĩa đen: **lấy các chuyến đi có thời lượng lớn hơn 400**. Đây là kiểu so sánh giữa một *trường* và một *giá trị cố định*.

Nhưng nếu muốn so sánh **giữa hai trường với nhau**, hoặc bạn muốn làm phép tính trong truy vấn? Lúc này, chúng ta cần gọi đến "trợ lý nâng cao": `$expr`.

### `$expr` là gì?

`$expr` cho phép bạn **viết truy vấn như đang viết biểu thức logic hoặc toán học**, nghĩa là bạn có thể:

- So sánh 2 trường (field)
- Áp dụng toán tử như `$gt`, `$eq`, `$add`, `$multiply`, v.v.
- Viết logic phức tạp thay vì chỉ tìm theo một giá trị cụ thể

**Ví dụ:**

```jsx
db.trips.find({
  $expr: {
    $gt: [ "$tripduration", 400 ]
  }
})
```

Điểm đặc biệt ở đây là thay vì viết `tripduration` như một *key*, giờ nó trở thành một *giá trị field* – nên phải thêm `$` phía trước: `"$tripduration"`.

Mongo hiểu: “Lấy mọi chuyến đi mà giá trị của trường `tripduration` lớn hơn 400”.

## 8. Truy vấn phi cấu trúc

### Truy vấn theo sự hiện diện của field với `$exists`

Khi làm việc với dữ liệu phi cấu trúc như MongoDB, không phải document nào cũng giống nhau 100%. Có document có field `ipo`, có document không. Có document có `funding_rounds`, có document chưa từng được gọi vốn.

Vậy nếu ta muốn **tìm tất cả những document mà có chứa một field cụ thể**, thì phải làm sao?

Toán tử `$exists` là công cụ giúp bạn kiểm tra sự hiện diện của một trường (field). Cú pháp rất tự nhiên:

```jsx
{ field: { $exists: true } }
```

Nghĩa là: *trả về những document mà field đó **tồn tại***.

**Ví dụ**

Bạn muốn lấy danh sách các công ty **đã có thông tin IPO và gọi vốn**:

```
db.companies.find({
  "ipo": { $exists: true },
  "funding_rounds": { $exists: true }
})
```

Truy vấn này lọc ra những document có **đồng thời cả 2 trường** `ipo` và `funding_rounds`.

### Kiểm tra **không tồn tại**

Nếu bạn cần lọc những document **không có** field `acquisition`, chỉ cần:

```jsx

{ "acquisition": { $exists: false } }
```

### Truy vấn theo kiểu dữ liệu với `$type`

Không phải lúc nào dữ liệu trong MongoDB cũng có **kiểu dữ liệu đồng nhất**. Cùng là trường `homepage_url`, có khi là chuỗi (string), có khi lại là null, có khi là object. Vậy làm sao để lọc ra những document **mà field có đúng kiểu dữ liệu ta cần**?

MongoDB lưu trữ dữ liệu ở dạng **BSON** (Binary JSON), và mỗi kiểu dữ liệu sẽ có một số hiệu riêng. Ví dụ:

| Kiểu dữ liệu | Tên | Mã số |
| --- | --- | --- |
| Double | `double` | 1 |
| String | `string` | 2 |
| Object | `object` | 3 |
| Array | `array` | 4 |

> Toàn bộ danh sách có tại đây: MongoDB BSON types
> 

**Ví dụ** 

Bạn muốn lọc tất cả các công ty có `homepage_url` là kiểu chuỗi:

```jsx
db.companies.find({
  "homepage_url": { $type: 2 }  // hoặc "string"
})
```

**Ví dụ nâng cao: chấp nhận nhiều kiểu dữ liệu**

Bạn muốn lọc tất cả các document có `homepage_url` là **chuỗi hoặc mảng**:

```
db.companies.find({
  "homepage_url": { $type: [2, 4] }
})
```

> Đây là cách cực kỳ hữu ích khi bạn đang kiểm tra chất lượng dữ liệu hoặc debug schema lỏng lẻo.
> 

## 9. Cursor Methods – Làm chủ luồng dữ liệu trả về từ MongoDB

Sau khi thực hiện `find()`, kết quả trả về không phải một mảng cố định mà là một **con trỏ (cursor)**. Cursor cho phép bạn thao tác linh hoạt với tập kết quả: đếm, lọc, phân trang, giới hạn, sắp xếp…

### `count()`: Đếm số document khớp với truy vấn

```jsx
db.trips.find({}).count()
```

> Trả về tổng số document tìm được.
> 
> 
> Dễ hiểu, nhưng **không nên dùng cho skip/limit**, hãy dùng `size()`.
> 

### `limit(n)`: Giới hạn số document trả về

```jsx
db.trips.find().limit(5)
```

> Lấy tối đa 5 document đầu tiên.
> 

### `skip(n)`: Bỏ qua `n` document đầu

```jsx
db.trips.find().skip(10)
```

> Dùng để phân trang. Ví dụ:
> 
> 
> Trang 2, mỗi trang 10 kết quả → `.skip(10).limit(10)`
> 

---

### `size()`: Kết hợp với skip/limit để đếm số lượng thực tế

```
db.trips.find().skip(10).limit(5).size()
```

> Trả về số lượng document sau khi áp dụng skip/limit.
> 
> 
> Khác với `count()` là đếm toàn bộ.
> 

---

### `sort()`: Sắp xếp theo field mong muốn

```
db.trips.find().sort({ "tripduration": 1 }) // tăng dần
db.trips.find().sort({ "tripduration": -1 }) // giảm dần
```

> Dùng số 1 cho tăng dần, -1 cho giảm dần.
> 

## 10. Projection – Chọn trường nào sẽ *được trả về* trong MongoDB

**Vấn đề đặt ra:** Khi bạn gọi

```
db.grades.find()
```

MongoDB sẽ trả về **toàn bộ document**, bao gồm mọi field: `_id`, `student_id`, `class_id`, `scores`, v.v.

Nhưng nếu bạn chỉ muốn xem **một vài trường nhất định**, làm sao để lọc bớt phần dư?

**Projection là giải pháp!**

```
js
CopyEdit
db.collection.find(query, projection)

```

Trong đó `projection` là một object xác định các field muốn *hiện (1)* hoặc *ẩn (0)*.

**Ví dụ:**

Chỉ lấy `student_id` và `class_id`, bỏ qua `scores`:

```jsx
db.grades.find(
  {},
  { "student_id": 1, "class_id": 1 }
)
```

> Kết quả sẽ chỉ bao gồm:
> 

```json
{
  "_id": ObjectId(...),
  "student_id": 1,
  "class_id": 302
}
```

**Ghi nhớ:**

- Dùng `1` để **include** field.
- Dùng `0` để **exclude** field.
- Không được **trộn lẫn 1 và 0** trong cùng một projection (ngoại trừ `_id`).

**Ví dụ:** loại bỏ `_id`, chỉ lấy `scores`:

```
db.grades.find({}, { "scores": 1, "_id": 0 })
```

## 11. Truy vấn tài liệu lồng nhau (Embedded Documents)

**Vấn đề:**

Một document trong MongoDB có thể chứa một object *lồng bên trong*, ví dụ:

```json
"address": {
  "city": "RIDGEWOOD",
  "zip": 11385,
  "street": "MENAHAN ST"
}
```

Vậy làm sao **truy vấn** đến `zip` nằm trong `address`?

**Cách truy vấn:**

Dùng **dot notation** (`tên_ngoài.tên_trong`):

```
db.inspections.find({
  "address.zip": 11385
})
```

> Truy vấn này sẽ trả về tất cả các document có address.zip = 11385.
> 

Trong MongoDB, bạn thường sẽ thấy dữ liệu được thiết kế theo **dạng lồng nhau** thay vì bảng như SQL. Việc biết cách truy vấn nested fields là điều cần thiết.

## 11. Truy vấn Embedded Document trong MongoDB

MongoDB hỗ trợ **document lồng nhau** (embedded documents). Bạn có thể truy vấn các giá trị **bên trong một document con** bằng cú pháp sử dụng dấu `.`.

```
db.collection.find({
  "embedded_field.subfield": value
})
```

**Ví dụ**

Giả sử document như sau:

```json
{
  address: {
    city: "RIDGEWOOD",
    zip: 11385,
    street: "MENAHAN ST"
  }
}
```

Muốn tìm các document có `zip = 11385` trong trường `address`:

```
db.inspections.find({
  "address.zip": 11385
})
```

→ Truy vấn này **đào sâu** vào document con `address` và chỉ ra cụ thể `zip`.

## 12. Truy vấn mảng trong MongoDB

Trong MongoDB, một field có thể là **mảng**. Vậy làm sao để tìm document mà:

- Mảng chứa một số giá trị nhất định?
- Mảng có độ dài cụ thể?

### `$all`: Truy vấn khi mảng **chứa đầy đủ các phần tử chỉ định**

```
db.collection.find({
  field: { $all: [value1, value2, ...] }
})
```

→ Trả về **mọi document** mà `field` là mảng và chứa **tất cả các giá trị trong mảng `$all`**, **không quan trọng thứ tự**.

**Ví dụ:**

```jsx
db.students.find({
  skills: { $all: ["Python", "MongoDB"] }
})
```

→ Trả về sinh viên biết cả **Python** và **MongoDB** (mảng `skills` có đủ 2 giá trị này).

### `$size`: Truy vấn khi mảng có **độ dài cụ thể**

```jsx
db.collection.find({
  field: { $size: n }
})
```

→ Trả về document mà `field` là mảng có **exactly n phần tử**.

**Ví dụ:**

```
db.students.find({
  skills: { $size: 3 }
})
```

→ Trả về sinh viên có **đúng 3 kỹ năng** trong mảng `skills`.

### `$all`: Chứa tất cả giá trị chỉ định (không cần đúng thứ tự)

```
db.students.find({
  skills: { $all: ["math", "english"] }
})
```

→ Trả về tất cả document mà trường `skills` chứa cả "math" và "english".

### `$size`: Độ dài mảng

```
db.students.find({
  hobbies: { $size: 2 }
})
```

→ Trả về các document mà trường `hobbies` là mảng có đúng **2 phần tử**.

### `$elemMatch`: Tìm phần tử trong mảng thỏa nhiều điều kiện cùng lúc

```
db.grades.find({
  scores: {
    $elemMatch: {
      type: "exam",
      score: { $gt: 80 }
    }
  }
})
```

→ Trả về các document mà trong mảng `scores` có **ít nhất một phần tử** thỏa:

- `type` là `"exam"`
- `score` lớn hơn `80`

## 13. Xoá Document trong MongoDB

MongoDB cung cấp 2 phương thức để **xoá document** trong collection:

### `deleteOne(filter)`

→ **Xoá duy nhất 1 document** đầu tiên **khớp với điều kiện**.

```jsx
db.student.deleteOne({ "name": "Anh" })
db.student.deleteOne({ "likes.best": "sport" })
```

→ Kết quả:

```json
{ acknowledged: true, deletedCount: 1 }
```

### `deleteMany(filter)`

→ **Xoá tất cả các document** khớp với điều kiện.

```
db.student.deleteMany({ "name": "Anh" })
```

→ Kết quả:

```json
{ acknowledged: true, deletedCount: 4 }
```

## 14. Cập nhật Document trong MongoDB

MongoDB hỗ trợ cập nhật document bằng hai phương thức chính:

### `updateOne(filter, update)`

→ **Cập nhật 1 document đầu tiên** phù hợp với `filter`.

```jsx
db.student.updateOne(
  { "name": "Thai" },
  { $set: { "name": "Anh" } }
)
```

### `updateMany(filter, update)`

→ **Cập nhật tất cả các document** khớp với điều kiện.

```jsx
db.student.updateMany(
  { "name": "Thai" },
  { $set: { "address": "Ha Noi" } }
)

db.student.updateMany(
  {},
  { $set: { "address": "Ha Noi" } }
)
```

### `$unset`: Xoá một field khỏi document

```jsx
db.collection.updateMany(
  { <filter> },
  { $unset: { <field>: "" } }
)
```

**Ý nghĩa:** Xoá field được chỉ định trong tất cả documents thỏa điều kiện.

**Ví dụ:**

```
db.student.updateMany(
  {},
  { $unset: { "address": "" } }
)
```

Tất cả document trong `student` sẽ bị xoá field `"address"`.

### `$rename`: Đổi tên một field

```jsx
db.collection.updateMany(
  { <filter> },
  { $rename: { "old_field": "new_field" } }
)
```

**Ví dụ:**

```
db.student.updateMany(
  {},
  { $rename: { "hobbies_list": "hobbies" } }
)
```

Đổi tên field `hobbies_list` thành `hobbies` trong toàn bộ document.

**Kết hợp `$unset` và `$rename`:**

Bạn có thể kết hợp cả hai như sau:

```
db.student.updateMany(
  {},
  {
    $unset: { "address": "" },
    $rename: { "hobbies_list": "hobbies" }
  }
)
```

### `$inc` – Tăng (hoặc giảm) giá trị số

```
db.collection.updateMany(
  { <filter> },
  { $inc: { <field>: value } }
)
```

Dùng để tăng (hoặc giảm nếu value âm) giá trị trường số.

**Ví dụ:**

```
db.student.updateMany(
  { "age": 20 },
  { $inc: { "age": 1 } }
)
```

Tăng tuổi từ 20 lên 21.

### `$push` – Thêm phần tử vào mảng

```
db.collection.updateMany(
  { <filter> },
  { $push: { <array_field>: value } }
)
```

Thêm phần tử vào cuối mảng.

**Ví dụ:**

```
db.student.updateMany(
  { "name": "Hoa" },
  { $push: { "address": "Ha Noi" } }
)
```

Thêm `"Ha Noi"` vào cuối mảng `address` của bạn Hoa.

### `$set` – Gán (hoặc ghi đè) giá trị mới

```
db.collection.updateMany(
  { <filter> },
  { $set: { <field>: value } }
)

```

Dùng để cập nhật hoặc tạo mới field với giá trị chỉ định.

**Ví dụ:**

```
db.student.updateMany(
  { "name": "Hoa" },
  { $set: { "address": "Ho Chi Minh" } }
)
```

Ghi đè địa chỉ cũ thành `"Ho Chi Minh"`.

# Tổng kết

![image.png](quartz/content/NoSQL%202281187f7c6a80368dbccbb8488bad12/image%2020.png)

# Quiz

Câu 1: Đâu là cú pháp đúng?

```jsx
//A
db.student.insert(
  { "_id": 100, 
    "name": 'Thai' }
)

//B
db.student.insert(
		{ "_id": "Thai', 
		  "name": 'Thai' }
)

//C
db.student.insert(
		{ "_id": 'Thai’;
		  "name": 'Thai' }
)

//D
db.student.insert(
		{ "_id": ['Thai'], 
		  "name": 'Thai' }
)
```

- Đáp án:
    
    **A**
    
    Hãy chú ý đến việc dùng đúng cặp dấu nháy (`"` và `'`) và kiểu dữ liệu hợp lý cho `_id`.