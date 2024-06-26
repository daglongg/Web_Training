# REGEX.

## Bài 1:  ^https:\/\/[a-z]+.fptu-ech.io$
* ^: Bắt đầu chuỗi.
* https:\/\/: Khớp với https://.
* [a-z]+: Một hoặc nhiều ký tự chữ thường (từ a đến z).
* \.fptu-ech\.io$: Khớp với .fptu-ech.io và kết thúc chuỗi.

![image](https://github.com/daglongg/Web_Training/assets/138242812/ac0550c5-4a53-408d-82f4-62c875985456)

==> ``https://ehc.fptu-ech.io``

## Bài 2: ^[+-]?((\d+(\.\d*)?)|(\.\d+))$

* ^[+-]?: Tùy chọn một dấu cộng hoặc trừ ở đầu chuỗi.
* (\d+(\.\d*)?)|(\.\d+)): Phần chính của số, có thể là:
* Một hoặc nhiều chữ số, tùy chọn theo sau bởi dấu chấm và không hoặc nhiều chữ số (ví dụ: 123, 123., 123.45).
*  Hoặc một dấu chấm theo sau bởi một hoặc nhiều chữ số (ví dụ: .45).

![image](https://github.com/daglongg/Web_Training/assets/138242812/94851dc5-843e-45e4-82e5-bbb047985dbc)

==> ``.45 or 0.45 or -0.45``

## Bài 3: ^[0-9a-fA-F]+$
* ^[0-9a-fA-F]: Bắt đầu bằng số hoặc từ A-F hoặc a-f. Cái này là hexadecimal.

![image](https://github.com/daglongg/Web_Training/assets/138242812/e347fd84-20f7-4853-b063-72442041d89b)

==> ``10F``

## Bài 4: ^(((0?[1-9]|1[012])/(0?[1-9]|1\d|2[0-8])|(0?[13456789]|1[012])/(29|30)|(0?[13578]|1[02])/31)/(19|[2-9]\d)\d{2}|0?2/29/((19|[2-9]\d)(0[48]|[2468][048]|[13579][26])|(([2468][048]|[3579][26])00)))$

* ^: Bắt đầu của chuỗi.
* ((0?[1-9]|1[012])/(0?[1-9]|1\d|2[0-8]): Tháng từ 01 đến 09 hoặc từ 10 đến 12.
* /: Dấu gạch chéo để phân tách giữa tháng và ngày.
* (0?[1-9]|1\d|2[0-8]): Ngày từ 01 đến 28.
* (0?[13456789]|1[012])/(29|30): Các tháng có ngày 29 và 30, không bao gồm tháng 2.
* (0?[13578]|1[02])/31: Các tháng có ngày 31.
* /(19|[2-9]\d)\d{2}: Năm từ 1900 đến 1999 hoặc từ 2000 trở đi
* 0?2/29/((19|[2-9]\d)(0[48]|[2468][048]|[13579][26])|(([2468][048]|[3579][26])00)))$ được sử dụng để kiểm tra ngày 29 tháng 2 trong năm nhuận

![image](https://github.com/daglongg/Web_Training/assets/138242812/612181e2-b1ef-43a8-8b9f-7639201aa3da)

==> ``01/31/2003``

## Bài 5: ^(?=\d)(?:(?:31(?!.(?:0?[2469]|11))|(?:30|29)(?!.0?2)|29(?=.0?2.(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00)))(?:\x20|$))|(?:2[0-8]|1\d|0?[1-9]))([-./])(?:1[012]|0?[1-9])\1(?:1[6-9]|[2-9]\d)?\d\d(?:(?=\x20\d)\x20|$))?(((0?[1-9]|1[012])(:[0-5]\d){0,2}(\x20[AP]M))|([01]\d|2[0-3])(:[0-5]\d){1,2})?$

* ^(?=\d): Đảm bảo rằng ký tự đầu tiên của chuỗi là một chữ số.
* (?:(?:31(?!.(?:0?[2469]|11))|(?:30|29)(?!.0?2)|29(?=.0?2.(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00)))(?:\x20|$))|(?:2[0-8]|1\d|0?[1-9])): Biểu thức chính quy này kiểm tra tính hợp lệ của ngày tháng, bao gồm cả năm nhuận
* ([-./]): Ký tự phân tách ngày (dấu gạch ngang, dấu chấm, hoặc dấu gạch chéo).
* (?:1[6-9]|[2-9]\d)?\d\d:  Năm, từ 1600 trở đi.
* (?:(?=\x20\d)\x20|$): Nếu có một khoảng trắng tiếp theo và sau đó là một số, hoặc kết thúc chuỗi.
* (((0?[1-9]|1[012])(:[0-5]\d){0,2}(\x20[AP]M))|([01]\d|2[0-3])(:[0-5]\d){1,2})?$: Thời gian theo định dạng 12 giờ, từ 01 đến 12, có thể có phút và giây, và AM hoặc PM. Hoặc theo định dạng 24 giờ, từ 00 đến 23, có thể có phút và giây.

![image](https://github.com/daglongg/Web_Training/assets/138242812/569392ba-8f77-4782-9723-c4f49e42c3aa)

==> ``31-12-2021 23:01``


## Bài 6: ^(?=\d)(?:(?!(?:(?:0?[5-9]|1[0-4])(?:\.|-|\/)10(?:\.|-|\/)(?:1582))|(?:(?:0?[3-9]|1[0-3])(?:\.|-|\/)0?9(?:\.|-|\/)(?:1752)))(31(?!(?:\.|-|\/)(?:0?[2469]|11))|30(?!(?:\.|-|\/)0?2)|(?:29(?:(?!(?:\.|-|\/)0?2(?:\.|-|\/))|(?=\D0?2\D(?:(?!000[04]|(?:(?:1[^0-6]|[2468][^048]|[3579][^26])00))(?:(?:(?:\d\d)(?:[02468][048]|[13579][26])(?!\x20BC))|(?:00(?:42|3[0369]|2[147]|1[258]|09)\x20BC))))))|2[0-8]|1\d|0?[1-9])([-.\/])(1[012]|(?:0?[1-9]))\2((?=(?:00(?:4[0-5]|[0-3]?\d)\x20BC)|(?:\d{4}(?:$|(?=\x20\d)\x20)))\d{4}(?:\x20BC)?)(?:$|(?=\x20\d)\x20))?((?:(?:0?[1-9]|1[012])(?::[0-5]\d){0,2}(?:\x20[aApP][mM]))|(?:[01]\d|2[0-3])(?::[0-5]\d){1,2})?$

* ^(?=\d): Bắt đầu chuỗi và đảm bảo rằng chuỗi bắt đầu bằng một chữ số (0-9).
* (?:(?!...)): Đây là một negative lookahead, nghĩa là chuỗi không được khớp với mẫu trong dấu ngoặc. Ngăn không cho ngày từ 05-09 hoặc từ 10-14 tháng 10 năm 1582. Ngăn không cho ngày từ 03-09 hoặc từ 10-13 tháng 09 năm 1752.
* (31(?!(?:\.|-|\/)(?:0?[2469]|11))|30(?!(?:\.|-|\/)0?2)|(?:29(?:(?!(?:\.|-|\/)0?2(?:\.|-|\/))|(?=\D0?2\D(?:(?!000[04]|(?:(?:1[^0-6]|[2468][^048]|[3579][^26])00))(?:(?:(?:\d\d)(?:[02468][048]|[13579][26])(?!\x20BC))|(?:00(?:42|3[0369]|2[147]|1[258]|09)\x20BC))))))|2[0-8]|1\d|0?[1-9]): Đây là phần để kiểm tra ngày hợp lệ trong tháng.
* ([-./]): Lưu trữ dấu phân cách (dấu gạch ngang, dấu chấm, hoặc dấu gạch chéo) giữa các thành phần ngày tháng.
* (1[012]|(?:0?[1-9])): Kiểm tra tháng hợp lệ từ 1 đến 12 hoặc từ 01 đến 09.
* \2: Đảm bảo rằng dấu phân cách giữa tháng và năm là giống với dấu phân cách giữa ngày và tháng.
* ((?=(?:00(?:4[0-5]|[0-3]?\d)\x20BC)|(?:\d{4}(?:$|(?=\x20\d)\x20)))\d{4}(?:\x20BC)?): Kiểm tra tính hợp lệ của năm (bao gồm cả năm BC nếu có).
* (?:$|(?=\x20\d)\x20): Đảm bảo rằng sau năm không có khoảng trắng nữa, hoặc nếu có thì phải là khoảng trắng tiếp theo.
* (?:(?:0?[1-9]|1[012])(?::[0-5]\d){0,2}(?:\x20[aApP][mM]))|(?:[01]\d|2[0-3])(?::[0-5]\d){1,2})?: Đây là phần để kiểm tra thời gian (nếu có).
* ?$: Đây là ký tự kết thúc của chuỗi, nó đảm bảo rằng biểu thức chính quy phải khớp đến cuối chuỗi.

![image](https://github.com/daglongg/Web_Training/assets/138242812/ad7ae42b-9930-45c3-8666-58e177bba071)

==> ``15-08-1945 08:30 AM``

## Bài 7: ^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$

* ([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5]): Khớp với một chữ số từ 0 đến 9 hoặc khớp với hai chữ số bắt đầu từ 1 đến 9 hoặc khớp với ba chữ số, bắt đầu bằng 1 và tiếp theo là hai chữ số từ 0 đến 9 hoặc khớp với ba chữ số, bắt đầu bằng 2, chữ số thứ hai là từ 0 đến 4, và chữ số cuối cùng là từ 0 đến 9 hoặc khớp với ba chữ số, bắt đầu bằng 25 và chữ số cuối cùng là từ 0 đến 5.
* ((([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}: Phần này xác định rằng địa chỉ IP cần có chính xác ba đoạn được phân tách bằng dấu chấm (.). Mỗi đoạn này phải tuân theo quy tắc đã mô tả ở trên.
* ([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$: Đoạn cuối cùng của địa chỉ IP, mô tả cũng như phần đầu của biểu thức này, khớp với một số từ 0 đến 255.

![image](https://github.com/daglongg/Web_Training/assets/138242812/8b332d52-9ddc-4d3a-955f-cf3e1aa5693f)

==> ``255.0.0.0``

## Bài 8: ^(0|\+84)(\s|\.)?((3[2-9])|(5[689])|(7[06-9])|(8[1-689])|(9[0-46-9]))(\d)(\s|\.)?(\d{3})(\s|\.)?(\d{3})$

* ^: Bắt đầu của chuỗi.
* (0|\+84): Phần tiền tố của số điện thoại có thể là 0 hoặc +84.
* (\s|\.)?: Dấu cách hoặc dấu chấm có thể có hoặc không.
* ((3[2-9])|(5[689])|(7[06-9])|(8[1-689])|(9[0-46-9])): Đây là các ký tự đầu số của các nhà mạng di động tại Việt Nam
* (\d): Ký tự số thứ hai của đầu số.
* (\s|\.)?: Dấu cách hoặc dấu chấm có thể có hoặc không.
* (\d{3}): Ba chữ số tiếp theo của số điện thoại.
* (\s|\.)?: Dấu cách hoặc dấu chấm có thể có hoặc không.
* (\d{3}): Ba chữ số cuối cùng của số điện thoại.
* $: Kết thúc chuỗi.

![image](https://github.com/daglongg/Web_Training/assets/138242812/5167cf4d-4b14-4237-ac81-0557eec8a584)

==> ``0793946535``

## Bài 9: ^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#\$%\^&\*]).{8,}$
* Biểu thức chính quy này được sử dụng để kiểm tra tính mạnh của mật khẩu, yêu cầu mật khẩu phải có ít nhất các yếu tố sau:
* Ít nhất một ký tự thường từ a đến z ((?=.*[a-z])).
* Ít nhất một ký tự hoa từ A đến Z ((?=.*[A-Z])).
* Ít nhất một chữ số từ 0 đến 9 ((?=.*[0-9])).
* Ít nhất một ký tự đặc biệt trong danh sách !@#$%^&* ((?=.*[!@#\$%\^&\*])).
* Độ dài của mật khẩu phải từ 8 ký tự trở lên (.{8,}).

![image](https://github.com/daglongg/Web_Training/assets/138242812/cb428b0a-7be2-4ce4-8d30-28dba0a2ea44)

==> ``Password1!``

## Bài 10: ^[^\s@]+@[^\s@]+\.[^\s@]+$
* Biểu thức chính quy này kiểm tra tính hợp lệ của địa chỉ email theo các tiêu chuẩn cơ bản, bao gồm:
* Phải có ký tự @ phân tách giữa phần username và domain.
* Phần username và domain không được bắt đầu hoặc kết thúc bằng khoảng trắng.
* Phần mở rộng của domain phải có ít nhất một dấu . để phân tách giữa domain và phần mở rộng.

![image](https://github.com/daglongg/Web_Training/assets/138242812/b7591c3d-1a3e-481b-b8d4-214cac9f8de6)

==> ``longdvhe172045@fpt.edu.vn``
