# The-basic-structure-of-React-Native
## The basic structure of React Native
### Trong một dự án React Native, các thành phần cơ bản thường bao gồm:

**1.App Entry File (index.js hoặc App.js):** Đây là điểm bắt đầu của ứng dụng, nơi ứng dụng được khởi tạo và chạy. index.js thường dùng để đăng ký component chính của ứng dụng, thường là App, với AppRegistry. App.js thường là nơi bạn định nghĩa component chính của mình. <br><br>

**2.Components:** Đây là các khối xây dựng cơ bản của bất kỳ ứng dụng React Native nào, bao gồm các thành phần được xác định trước như View, Text, và Button, cũng như các thành phần tự tạo. Các thành phần này được tổ chức vào các file và thư mục theo chức năng hoặc tính năng. <br><br>

**3.Navigation:** Thành phần quản lý việc di chuyển giữa các màn hình hoặc các phần khác nhau của ứng dụng. Các thư viện phổ biến cho điều này bao gồm **React Navigation** và **React Native Navigation.** <br><br>
 
**4.Styles:** Kiểu dáng được quản lý thông qua JavaScript, sử dụng cú pháp tương tự như **CSS.** **Styles** có thể được áp dụng trực tiếp cho các thành phần hoặc được tổ chức vào các file riêng biệt. <br><br>

**5.Assets:** Bao gồm hình ảnh, **font, và các file media khác.** Các assets này thường được lưu trong thư mục **assets** và có thể được tham chiếu trực tiếp trong code. <br><br>

**6.Utilities/Helpers:** Các **function và module** hỗ trợ thực hiện các tác vụ phổ thông hoặc lặp lại, như định dạng **ngày tháng, xử lý chuỗi, v.v.** <br><br>

**7.State Management:** Cấu trúc quản lý trạng thái của ứng dụng. Có thể sử dụng **React's Context API, Redux, MobX,** hoặc các thư viện khác để quản lý trạng thái. <br><br>

**8.API Calls:** Code để giao tiếp với các **backend service** hoặc **external APIs,** thường được tổ chức trong các **module hoặc services** riêng biệt. <br><br>

**9.Tests:** Bao gồm **unit tests, integration tests, và end-to-end tests.** React Native hỗ trợ testing thông qua các thư viện như **Jest, Detox, và Enzyme.** <br><br>

**10.Configurations:** File cấu hình cho ứng dụng, bao gồm các biến môi trường, cấu hình cho các platform cụ thể (iOS/Android), và các cài đặt khác. <br><br>

**11.Package.json:** File này quản lý các dependency của dự án, cũng như định nghĩa các scripts để chạy ứng dụng, build, test, v.v. <br><br>

Cách tổ chức và mức độ phức tạp của các thành phần này có thể thay đổi tùy thuộc vào quy mô và yêu cầu cụ thể của dự án. <br><br>

https://chat.openai.com/c/6bbba98b-0571-4b33-9f8e-26679a1fb666 <br><br>
https://gemini.google.com/app/c7094ffb31c840b1  <br><br>


### Component trong React-Native
![image](https://github.com/Experimenters1/The-basic-structure-of-React-Native/assets/64000769/b50723ae-16c6-4e18-9361-e1182dce6de1) <br><br>
Vòng đời của component trong React Native tương tự như trong React dành cho phát triển web, vì React Native được xây dựng dựa trên cùng các nguyên tắc. Vòng đời của một component trong React và React Native bao gồm các giai đoạn: khởi tạo (mounting), cập nhật (updating), và dỡ bỏ (unmounting). Mỗi giai đoạn có một bộ các phương thức vòng đời riêng, cho phép bạn chạy code tại các thời điểm cụ thể trong suốt vòng đời. <br><br>
#### Giai đoạn Khởi tạo (Mounting Phase)
 Là giai đoạn **component** được tạo ra và thêm vào **DOM.** Ở giai đoạn này, các hàm **constructor(), getDerivedStateFromProps(), render(), và componentDidMount()** thường được gọi.
 
Đây là giai đoạn khi component được tạo và đưa vào DOM (hoặc giao diện người dùng gốc trên thiết bị di động trong trường hợp của React Native). Các phương thức vòng đời chính trong giai đoạn này là:  <br><br>
**+)constructor(props):** Đây là phương thức đầu tiên được gọi khi một **component** được tạo. Nó được dùng để khởi tạo **state**, liên kết các phương thức xử lý sự kiện với một thể hiện **(instance) của component.** <br><br>
**+)static getDerivedStateFromProps(props, state):** Phương thức này được gọi ngay trước khi **render** các **element lên DOM.** Nó cho phép **component** cập nhật state bên trong của nó dựa trên sự thay đổi của props. <br><br>
**+)render():** Phương thức **render** là bắt buộc và chịu trách nhiệm mô tả giao diện sẽ được **render lên DOM.** Đây là phương thức duy nhất được yêu cầu trong một **class component.** <br><br>
**+)componentDidMount():** Phương thức này được gọi sau khi **component** được gắn vào **DOM (hoặc native view).** Nó được sử dụng để thao tác với **DOM,** thực hiện các yêu cầu mạng và tích hợp với các framework JavaScript khác.<br><br>

#### Giai đoạn Cập nhật (Updating Phase) 
Là giai đoạn **component** được cập nhật dựa trên sự thay đổi của **props hoặc state.** Các hàm **getDerivedStateFromProps(), shouldComponentUpdate(), render(), và componentDidUpdate()** thường được gọi.

Giai đoạn này bắt đầu khi **state hoặc props** của **component** thay đổi và nó cần được **render** lại. Các phương thức được gọi trong giai đoạn này là: <br><br>

**+)static getDerivedStateFromProps(props, state):** Được gọi trước khi quá trình **render** lại bắt đầu, cho phép cập nhật **state dựa trên props** mới. <br><br>
**+)shouldComponentUpdate(nextProps, nextState):** Cho phép **component** quyết định có nên tiếp tục **render** lại hay không. Đây là một cách để tối ưu hiệu suất.<br><br>
**+)render()** <br><br>
**+) getSnapshotBeforeUpdate(prevProps, prevState):** Phương thức này được gọi ngay trước khi **output** được **render** gần đây nhất được áp dụng vào DOM (ví dụ). Nó cho phép **component** lấy một số thông tin từ DOM (ví dụ: vị trí cuộn) trước khi nó có khả năng bị thay đổi. <br><br>
**+)componentDidUpdate(prevProps, prevState, snapshot):** Được gọi sau khi **component** được cập nhật trong DOM. Hữu ích cho các thao tác DOM và yêu cầu mạng dựa trên state mới. <br><br>

#### Giai đoạn Dỡ bỏ (Unmounting Phase)  <br><br>

Giai đoạn này xảy ra khi một component bị loại bỏ khỏi DOM:

**+)componentWillUnmount():** Phương thức này được gọi ngay trước khi **component** bị dỡ bỏ và hủy. Nó hữu ích cho việc thực hiện các tác vụ dọn dẹp như vô hiệu hóa bộ hẹn giờ, hủy yêu cầu mạng hoặc dọn dẹp bất kỳ đăng ký nào được tạo trong **componentDidMount.** <br><br>
###
Bên cạnh các phương thức vòng đời, **component trong React** còn có các thuộc tính lớp như **state và props.** Ngoài ra còn có các **API** liên quan đến vòng đời như **setState() và forceUpdate().** Bạn có thể sử dụng **setState() để thay đổi state của component và forceUpdate() để buộc component render lại.** <br><br>

**React** đang không ngừng phát triển và một số phương thức vòng đời đã bị gỡ bỏ để ủng hộ các cách thực hành tốt hơn (ví dụ như tránh sử dụng **componentWillMount, componentWillReceiveProps và componentWillUpdate** trong code mới). Luôn tham khảo tài liệu React mới nhất để có thông tin cập nhật chính xác. <br><br>

### SafeAreaView

**SafeAreaView** là một **component wrapper** mà **React Native** cung cấp để giúp đảm bảo rằng nội dung và giao diện không bị che khuất bởi các thanh điều hướng **(navigation bars)**, thanh **tab**, các vùng tai thỏ **(notch)** trên iPhone, hoặc các vùng an toàn khác trên màn hình của thiết bị. Sử dụng **SafeAreaView** giúp bạn dễ dàng quản lý **layout** của ứng dụng sao cho nội dung của bạn luôn được hiển thị đúng cách và không bị cắt xén hay che khuất bởi các yếu tố giao diện của hệ điều hành. <br><br>

Khi bạn đặt các **component** khác bên trong **SafeAreaView**, bạn có thể yên tâm rằng chúng sẽ được đặt trong **"khu vực an toàn"** của màn hình, tránh xa các vùng không an toàn như đã nói trên. <br><br>

## StyleSheet

**StyleSheet** là một cách mà **React Native** cung cấp để bạn khai báo các **style** (các quy tắc thiết kế giao diện) cho ứng dụng của mình một cách có cấu trúc và tối ưu.  **StyleSheet.create** là một hàm giúp bạn tạo ra một đối tượng **style** từ các định nghĩa **style bằng JavaScript**. Việc này không chỉ giúp bạn quản lý **style** dễ dàng hơn (khi bạn tách **style** ra khỏi **logic component**), mà còn giúp tăng hiệu suất bởi vì **React Native** sẽ biết được các **style** nào có thể được tối ưu hóa và chia sẻ giữa các **component.** <br><br>


## Trong TypeScript : 
**interface :** được sử dụng để định nghĩa một **shape** hoặc cấu trúc cho một **object.** Nó cho phép bạn xác định các thuộc tính và kiểu dữ liệu của chúng mà một **object** nên có. Trong trường hợp của **React** hoặc **React Native components**, **interface** thường được sử dụng để xác định kiểu của **props** (thuộc tính được truyền vào **component**). <br><br>

```typescript
interface MyComponentProps {
  name: string;
}

```

Trong đoạn code trên, **interface MyComponentProps** định nghĩa một cấu trúc cho **props của component MyComponent**, với một yêu cầu rằng mọi **object props** truyền vào **MyComponent** phải có một thuộc tính **name** với kiểu dữ liệu là **string.** <br><br>

Điều này có nghĩa là: <br><br>

+ ) Khi bạn sử dụng **MyComponent** trong code của mình, bạn cần phải cung cấp một **prop name** với kiểu dữ liệu là **string.** <br><br>
+ ) **TypeScript** sẽ kiểm tra ở thời điểm biên dịch để đảm bảo rằng **MyComponent** được sử dụng đúng cách, với một **prop name** có kiểu dữ liệu đúng như đã định nghĩa. <br><br>

Việc sử dụng **interface** như vậy giúp tăng cường kiểm soát kiểu dữ liệu trong ứng dụng của bạn, giảm thiểu lỗi do sai kiểu dữ liệu và làm cho code của bạn trở nên dễ đọc và dễ bảo trì hơn. Nó cũng giúp phát triển ứng dụng hiệu quả hơn bởi vì các lỗi kiểu dữ liệu có thể được phát hiện sớm trong quá trình phát triển, trước khi chúng gây ra vấn đề trong ứng dụng chạy thực tế.<br><br>

### 1.View 
**View** là thành phần **container** cơ bản dùng để bao bọc và tổ chức các thành phần khác 

```typescript
import React from 'react';
import { View, StyleSheet } from 'react-native';

const ViewExample = () => (
  <View style={styles.container}>
    {/* Thêm các thành phần khác vào đây */}
  </View>
);

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f0f0',
  },
});

export default ViewExample;


```

### 2. Text

**Text** dùng để hiển thị văn bản. 
```typescript
import React from 'react';
import { Text, StyleSheet } from 'react-native';

const TextExample = () => <Text style={styles.textStyle}>Hello, React Native!</Text>;

const styles = StyleSheet.create({
  textStyle: {
    fontSize: 24,
    fontWeight: 'bold',
    color: '#333',
  },
});

export default TextExample;

```

### TouchableOpacity và Button 

+ ) **TouchableOpacity** cho phép tạo thành phần có thể tương tác với hiệu ứng làm mờ khi chạm vào và cho phép tùy chỉnh kiểu dáng nhiều hơn. <br>
+ ) **Button** cung cấp một nút bấm đơn giản với ít tùy chọn tùy chỉnh kiểu dáng. <br>

#### TouchableOpacity Example  : 
```typescript
import React from 'react';
import { TouchableOpacity, Text, StyleSheet } from 'react-native';

const TouchableOpacityExample = () => (
  <TouchableOpacity
    style={styles.buttonStyle}
    onPress={() => alert('TouchableOpacity pressed')}
  >
    <Text style={styles.textStyle}>Press Me</Text>
  </TouchableOpacity>
);

const styles = StyleSheet.create({
  buttonStyle: {
    backgroundColor: '#007bff',
    padding: 10,
    borderRadius: 5,
  },
  textStyle: {
    color: '#ffffff',
    fontSize: 18,
  },
});

export default TouchableOpacityExample;

```

#### Button Example : 
```typescript
import React from 'react';
import { Button, View, StyleSheet } from 'react-native';

const ButtonExample = () => (
  <View style={styles.container}>
    <Button
      title="Press Me"
      onPress={() => alert('Button pressed')}
      color="#841584"
    />
  </View>
);

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
});

export default ButtonExample;



```

[prop stae là gì](https://www.google.com/search?q=prop+stae+l%C3%A0+g%C3%AC&sca_esv=5b98a6ebe0c52b0a&sca_upv=1&rlz=1C5CHFA_enVN1013VN1013&sxsrf=ACQVn0-46-jH6Gu7NsuX8nv0fTKlIOhKxQ%3A1712226094630&ei=Ln8OZuXXJe2u2roP4KG30Ag&udm=&ved=0ahUKEwjlppShq6iFAxVtl1YBHeDQDYoQ4dUDCBA&uact=5&oq=prop+stae+l%C3%A0+g%C3%AC&gs_lp=Egxnd3Mtd2l6LXNlcnAiEXByb3Agc3RhZSBsw6AgZ8OsMgoQIRgKGKABGMMEMgoQIRgKGKABGMMESNI0UABYmhtwAXgBkAEAmAGjAaABgAeqAQMxLja4AQPIAQD4AQGYAgigAp4HwgIFEAAYgATCAgYQABgHGB7CAgcQABiABBgNwgIGEAAYHhgNwgIKEAAYBRgeGA0YD8ICCBAAGAgYHhgNwgIKEAAYCBgeGA0YD8ICCBAhGKABGMMEmAMAkgcDMS43oAfgJA&sclient=gws-wiz-serp) <br><br>


[react native cơ bản](https://www.google.com/search?q=react+native+c%C6%A1+b%E1%BA%A3n&rlz=1C5CHFA_enVN1013VN1013&oq=react+natve+cobna&gs_lcrp=EgZjaHJvbWUqCQgBEAAYDRiABDIGCAAQRRg5MgkIARAAGA0YgAQyBggCEEUYQDIGCAMQRRhAMgYIBBBFGEDSAQkxMzQ3MWowajeoAgCwAgA&sourceid=chrome&ie=UTF-8) <br><br>

[Vòng đời của component](https://www.google.com/search?q=V%C3%B2ng+%C4%91%E1%BB%9Di+c%E1%BB%A7a+component&rlz=1C5CHFA_enVN1013VN1013&oq=V%C3%B2ng+%C4%91%E1%BB%9Di+c%E1%BB%A7a+component&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIHCAEQABiABDIHCAIQABiABNIBBzI3OGowajeoAgCwAgA&sourceid=chrome&ie=UTF-8) <br><br>




