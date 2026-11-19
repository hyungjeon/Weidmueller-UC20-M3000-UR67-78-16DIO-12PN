# Hệ thống Remote I/O u-remote UR67 – Mô-đun I/O IP67 – Sổ tay vận hành (bản dịch tiếng Việt)

Dịch từ file `U_Remote_67.pdf` (bản tiếng Trung, 27 trang, Weidmüller, Revision 02 / tháng 1 năm 2026).
Mô-đun: UR67-PN-78-8IOL-12-P (3076230000), UR67-EC-78-8IOL-12-P (3076240000), UR67-PN-78-16DIO-12-P (3076250000), UR67-EC-78-16DIO-12-P (3076260000), UR67-IOL-H-16DIO-12-P (3076270000).

> Ghi chú: phần dịch giữ nguyên tên tín hiệu, tên chân, mã sản phẩm. Trang 26–27 (bản vẽ kích thước lắp đặt) chỉ có hình, không có chữ để dịch.

---

## Mục lục (trang 3)

1. Về tài liệu: 1.1 Ký hiệu và giải thích; 1.2 Định dạng dữ liệu; 1.3 Phiên bản phần mềm và phần cứng
2. An toàn: 2.1 Lưu ý an toàn; 2.2 Mục đích sử dụng; 2.3 Thông tin tuân thủ; 2.4 Tương thích điện từ UR67 I/O
3. Tổng quan hệ thống: 3.1 Thông số cổng; 3.2 Thông số giao thức; 3.3 Thông số IO-Link; Phụ kiện
4. Tổng quan mô-đun: 4.1–4.9 từng mô-đun và sơ đồ chân; 4.10 Thông số kỹ thuật
5. An toàn khi lắp đặt: 5.1 Chuẩn bị trước khi lắp; 5.2 Lắp đặt và nối đất

---

## 1. Về tài liệu

### 1.1 Ký hiệu và giải thích

Các ký hiệu trong tài liệu và sản phẩm theo quy ước sau:

- Ký hiệu **Nguy hiểm**: nguy hiểm do không làm đúng yêu cầu, có thể dẫn đến thương vong.
- Ký hiệu **Cảnh báo/Chú ý**: nguy hiểm do không làm đúng yêu cầu, có thể gây thương tích nhẹ hoặc vừa và hư hỏng thiết bị.
- Ký hiệu **Lưu ý**: bổ sung hoặc giải thích cần thiết cho phần mô tả thao tác.
- Ký hiệu **Linh kiện nhạy tĩnh điện**: có thể xuất hiện trong thông báo an toàn của sản phẩm.

### 1.2 Định dạng dữ liệu

Cấu trúc dữ liệu của mọi thông tin của mô-đun (dữ liệu quá trình, tham số…) tham chiếu theo cấu trúc dữ liệu chuẩn trong tham số mô-đun:

| Mô-đun                | Định dạng dữ liệu        |
| --------------------- | ------------------------ |
| UR67-PN-78-8IOL-12-P  | Motorola, tức big-endian |
| UR67-PN-78-16DIO-12-P | Motorola, tức big-endian |
| UR67-EC-78-8IOL-12-P  | Intel, tức little-endian |
| UR67-EC-78-16DIO-12-P | Intel, tức little-endian |
| UR67-IOL-H-16DIO-12-P | Intel, tức little-endian |

Giải thích:

- Chế độ Motorola (big-endian): byte cao của dữ liệu nằm ở địa chỉ thấp trong bộ nhớ, byte thấp nằm ở địa chỉ cao.
- Chế độ Intel (little-endian): ngược lại; byte thấp nằm ở địa chỉ thấp, byte cao nằm ở địa chỉ cao.

### 1.3 Phiên bản phần mềm và phần cứng

Phiên bản phần mềm (firmware):

| Mã đặt hàng | Model                 | Phiên bản |
| ----------- | --------------------- | --------- |
| 3076230000  | UR67-PN-78-8IOL-12-P  | 1.0.36    |
| 3076240000  | UR67-EC-78-8IOL-12-P  | 1.0.24    |
| 3076250000  | UR67-PN-78-16DIO-12-P | 1.14      |
| 3076260000  | UR67-EC-78-16DIO-12-P | 1.9       |
| 3076270000  | UR67-IOL-H-16DIO-12-P | 1.7       |

Tệp mô tả thiết bị:

| Mã đặt hàng | Model                 | Phiên bản |
| ----------- | --------------------- | --------- |
| 3076230000  | UR67-PN-78-8IOL-12-P  | 1.0.36    |
| 3076240000  | UR67-EC-78-8IOL-12-P  | 1.0.24    |
| 3076250000  | UR67-PN-78-16DIO-12-P | 2.35      |
| 3076260000  | UR67-EC-78-16DIO-12-P | 1.9       |
| 3076270000  | UR67-IOL-H-16DIO-12-P | 1.1       |

---

## 2. An toàn

Chương này có các lưu ý an toàn chung khi vận hành mô-đun u-remote IP67. Lưu ý riêng cho từng tác vụ và tình huống sử dụng xem ở các chương tương ứng.

Mọi thao tác phải do kỹ sư chuyên môn đã được đào tạo và nắm rõ quy định an toàn của sản phẩm thực hiện. Tài liệu này phải để ở nơi phù hợp để người vận hành tra cứu bất cứ lúc nào.

### 2.1 Lưu ý an toàn

- Khi mô-đun đang chạy mà cần thao tác, phải thiết kế thiết bị dừng khẩn cấp và bảo đảm thiết bị này không bị mất tác dụng.
- Khi mô-đun u-remote hỏng mà không xử lý được tại hiện trường, phải gửi sản phẩm về Weidmüller. Nếu sản phẩm bị tự ý tháo mở khi chưa được phép, Weidmüller không chịu trách nhiệm về sản phẩm đó.
- Mọi thiết bị nối vào mô-đun phải đáp ứng yêu cầu của EN 61558-2-6. Chỉ được lắp cáp và phụ kiện khi thỏa mãn các yêu cầu về an toàn, tương thích điện từ và (nếu áp dụng) thiết bị đầu cuối viễn thông. Thông tin về cáp và phụ kiện được phép lắp có trong sổ tay này hoặc hỏi Weidmüller.
- **Phóng tĩnh điện**: sản phẩm u-remote có thể bị hỏng do phóng tĩnh điện. Khi xử lý phải tuân thủ biện pháp chống tĩnh điện (ESD) theo IEC 61340-5-1 và IEC 61340-5-2. Việc đóng gói, mở gói, lắp và tháo thiết bị phải do người có chuyên môn thực hiện.
- **Cầu chì**: người vận hành phải cài đặt cần thiết để thiết bị được bảo vệ quá tải. Nguồn 24 V DC cấp cho hệ thống phải thuộc loại SELV (điện áp cực thấp an toàn). Cầu chì phía trước phải được thiết kế để không vượt quá dòng tải tối đa. Dòng tải tối đa cho phép của linh kiện u-remote xem trong thông số kỹ thuật. Người vận hành phải căn cứ tiêu chuẩn IEC 62305 để quyết định có cần chống sét lan truyền bổ sung không. Điện áp vượt ±30 V có thể làm hỏng mô-đun. Phải dùng nguồn có cách ly tin cậy.
- **Nối đất chức năng (FE)**: mỗi mô-đun UR67 có một đầu nối đất, điểm nối ghi "FE". Thông tin thêm ở chương 5.
- **Che chắn (shield)**: dây có che chắn phải nối bằng đầu cắm có che chắn và theo tiêu chuẩn liên quan.

### 2.2 Mục đích sử dụng

- UR67-PN-78-8IOL-12-P và UR67-PN-78-16DIO-12-P là thiết bị vào/ra phân tán trong mạng PROFINET (RT/IRT). Trong đó UR67-PN-78-8IOL-12-P có thể dùng làm master IO-Link.
- UR67-EC-78-8IOL-12-P và UR67-EC-78-16DIO-12-P là thiết bị vào/ra phân tán trong mạng EtherCAT. Trong đó UR67-EC-78-8IOL-12-P có thể dùng làm master IO-Link.
- UR67-IOL-H-16DIO-12-P là thiết bị vào/ra phân tán hỗ trợ IO-Link hub.
- Các sản phẩm này được thiết kế cho môi trường công nghiệp, phải dùng trong phạm vi thông số kỹ thuật đã nêu. Thiết bị cần nối phải đáp ứng EN 61558-2-4 và EN 61558-2-6. Môi trường công nghiệp được xác định rõ để người tiêu dùng không nối trực tiếp vào lưới hạ áp công cộng. Khi dùng trong khu dân cư, thương mại và công nghiệp nhẹ, phải có biện pháp bổ sung.
- Ngoài các trường hợp mô tả trong sổ tay, mọi sửa đổi phần cứng hoặc phần mềm của sản phẩm chỉ do Weidmüller thực hiện.
- Chỉ khi vỏ được lắp hoàn chỉnh mới bảo đảm vận hành không lỗi. Tuân thủ quy định trong tài liệu cũng là một phần của mục đích sử dụng.

### 2.3 Thông tin tuân thủ

Mô-đun có tích hợp thành phần phần mềm mã nguồn mở: Không.

### 2.4 Tương thích điện từ UR67 I/O

Dòng sản phẩm UR67 tuân thủ chỉ thị EU 2014/30/EU (EMC).

---

## 3. Tổng quan hệ thống

Mô-đun UR67-PN-78 là mô-đun IO dựa trên giao thức PROFINET, vỏ nhựa đạt cấp bảo vệ IP67. Có hai thiết kế:

- **UR67-PN-78-8IOL-12-P**: 8 cổng, mỗi cổng hỗ trợ master IO-Link hoặc 2 kênh vào/ra số.
- **UR67-PN-78-16DIO-12-P**: 8 cổng, mỗi cổng có thể cấu hình thành 2 kênh vào/ra số.

Mô-đun UR67-EC-78 dựa trên giao thức EtherCAT, vỏ nhựa IP67, có hai thiết kế:

- **UR67-EC-78-8IOL-12-P**: 8 cổng, mỗi cổng hỗ trợ master IO-Link hoặc 2 kênh vào/ra số.
- **UR67-EC-78-16DIO-12-P**: 8 cổng, mỗi cổng có thể cấu hình thành 2 kênh vào/ra số.

Mô-đun **UR67-IOL-H-16DIO-12-P** là mô-đun slave IO-Link (HUB), vỏ nhựa IP67, có 8 cổng, mỗi cổng có thể cấu hình thành 2 kênh vào/ra số.

### 3.1 Thông số cổng

Các cổng khác nhau của mọi mô-đun được định nghĩa bằng màu hoặc kích thước khác nhau để người dùng dễ phân biệt:

- **Mạng PROFINET (màu xanh lá)**: 2 cổng, đầu cắm M12 D-code 4 cực (vào và ra), tốc độ truyền tối đa 100 Mbps.
- **Cổng I/O (màu đen)**: 8 cổng, đầu cắm M12 A-code 5 cực.
- **Cổng nguồn (màu đen)**: 2 cổng, đầu cắm 7/8" 5 cực.

### 3.2 Thông số giao thức

**Địa chỉ MAC**: UR67-PN là mô-đun hỗ trợ mạng PROFINET, mỗi mô-đun có ba địa chỉ MAC (một cho thân mô-đun, hai cho cổng Ethernet), được gán duy nhất từ nhà máy, người dùng không thể thay đổi. Địa chỉ MAC in trên thân mô-đun.

**Switch Ethernet tích hợp**: mỗi mô-đun hỗ trợ PROFINET tích hợp hai switch Ethernet truyền thẳng, hỗ trợ cấu trúc vòng và tuyến tính.

**Đặc tính sản phẩm PROFINET**: UR67-PN hỗ trợ thiết bị PROFINET IO RT, IRT, nghĩa là dữ liệu quá trình truyền thời gian thực. Hỗ trợ các tính năng:

- DCP: tự động gán địa chỉ IP cho thiết bị.
- Thay thế tiện lợi: khi mô-đun giao diện hỏng cần thay, không cần PG/PC cấu hình lại thiết bị.
- LLDP: phát hiện thiết bị lân cận.
- MRP: xây dựng mạng PROFINET dự phòng (vòng) không cần switch.
- SNMP: giám sát thiết bị mạng.

**Đặc tính sản phẩm EtherCAT**: UR67-EC hỗ trợ: EoE (nâng cấp firmware), CoE (truyền dữ liệu quá trình, chẩn đoán và tham số), DC (đồng hồ phân tán đồng bộ).

**Tệp mô tả thiết bị**: PROFINET: GSDML; EtherCAT: ESI; IO-Link: IODD.

### 3.3 Thông số IO-Link

- **Lưu tham số**: lưu và giám sát tham số thiết bị IO-Link và master IO-Link để dễ thay từng thành phần. Chỉ dùng được khi thiết bị hoặc master IO-Link hỗ trợ (IO-Link spec V1.1.3 trở lên; cần kiểm tra tương thích giữa các phiên bản).
- **Xác thực thiết bị**: khi bật, thiết bị kiểm tra dữ liệu nhận dạng của thiết bị IO-Link nối vào có khớp cài đặt trong master IO-Link không. Chỉ khi tất cả khớp, IO-Link mới truyền dữ liệu.
- **Tham số hóa thiết bị IO-Link**: có thể dùng khối chức năng Siemens IO_LINK_CALL (STEP 7) và IO_LINK_DEVICE (TIA Portal) để tham số hóa thiết bị IO-Link qua PROFINET.

### Phụ kiện

**Nắp bảo vệ**: Mô-đun chỉ đạt IP67 khi mọi cổng đang dùng đều cắm cáp và khóa đúng, các cổng không dùng đều lắp nắp bảo vệ đúng.

| Kích thước | Mục đích         | Ghi chú                                                        |
| ---------- | ---------------- | -------------------------------------------------------------- |
| M12        | Kết nối cảm biến | Cắm đầu nối và khóa đúng, hoặc lắp nắp bảo vệ đúng để đạt IP67 |
| M12        | Bus-out          | Cắm đầu nối và khóa đúng, hoặc lắp nắp bảo vệ đúng để đạt IP67 |
| 7/8"       | Nguồn            | Cắm đầu nối và khóa đúng để đạt IP67; nắp cao su chỉ chống bụi |

**Nhãn đánh dấu**: có thể dùng nhãn tiêu chuẩn của Weidmüller cho mô-đun và cổng. Nhãn 13,5 mm PA66 trong suốt: ESG 8/13.5/43.3 SAI AU, mã 1912130000. Tất cả nhãn đều in được bằng máy in nhãn Weidmüller.

**Đầu nối và cáp**: để dễ chọn cáp và đầu nối, nên dùng công cụ chọn sản phẩm trên website Weidmüller. Một số mã đề xuất:

| Mã         | Mô tả              | Dài (m) | Loại                               |
| ---------- | ------------------ | ------- | ---------------------------------- |
| 2608080100 | SAIL-M12G-5-1.0UA  | 1       | M12 5 lõi đầu đực, một đầu hở, PUR |
| 2608080300 | SAIL-M12G-5-3.0UA  | 3       | như trên                           |
| 2608080500 | SAIL-M12G-5-5.0UA  | 5       | như trên                           |
| 2608081000 | SAIL-M12G-5-10UA   | 10      | như trên                           |
| 2608110100 | SAIL-M12BG-5-1.0UA | 1       | M12 5 lõi đầu cái, một đầu hở, PUR |
| 2608110300 | SAIL-M12BG-5-3.0UA | 3       | như trên                           |
| 2608110500 | SAIL-M12BG-5-5.0UA | 5       | như trên                           |
| 2608111000 | SAIL-M12BG-5-10UA  | 10      | như trên                           |

---

## 4. Tổng quan mô-đun

### 4.1 UR67-PN-78-8IOL-12-P (Master IO-Link)

Mô-đun IO phân tán có chức năng IO-Link cho mạng PROFINET. Có 8 giao diện tín hiệu (M12, 5 cực, A-code), 2 giao diện truyền thông (M12, 4 cực, D-code), 2 giao diện nguồn (7/8", 5 cực). Mô-đun có 8 cổng IO-Link hoặc 16 kênh vào/ra số, chức năng kênh cấu hình bằng phần mềm.

Đèn chẩn đoán và trạng thái:

| Đèn             | Màu       | Mô tả                                 |
| --------------- | --------- | ------------------------------------- |
| US              | Xanh/Đỏ   | Trạng thái nguồn hệ thống và cảm biến |
| UL              | Xanh/Đỏ   | Trạng thái nguồn cơ cấu chấp hành     |
| BF              | Xanh/Đỏ   | Trạng thái bus                        |
| DIA             | Xanh/Đỏ   | Chẩn đoán mô-đun                      |
| LINK/ACT P1, P2 | Xanh/Vàng | Trạng thái mạng                       |
| 1..8 AB         | Xanh/Đỏ   | Trạng thái vào/ra / IO-Link           |

Các bộ phận trên hình: 1 đèn trạng thái kênh A; 2 cổng IO A-Code; 3 đèn trạng thái kênh B; 4 đèn trạng thái mô-đun; 5 cổng nguồn vào 7/8" (đực); 6 cổng PROFINET vào D-Code; 7 cổng nguồn ra 7/8" (cái); 8 cổng PROFINET ra D-Code; 9 nối đất.

### 4.2 UR67-EC-78-8IOL-12-P (Master IO-Link, EtherCAT)

Mô-đun IO phân tán có IO-Link cho mạng EtherCAT. 8 giao diện tín hiệu (M12, 5 cực, loại A), 2 giao diện truyền thông (M12, 4 cực, loại D), 2 giao diện nguồn (7/8", 5 cực). 8 cổng IO-Link hoặc 16 kênh vào/ra số, cấu hình bằng phần mềm.

| Đèn              | Màu     | Mô tả                       |
| ---------------- | ------- | --------------------------- |
| US               | Xanh/Đỏ | Nguồn hệ thống và cảm biến  |
| UL               | Xanh/Đỏ | Nguồn cơ cấu chấp hành      |
| RUN              | Xanh/Đỏ | Trạng thái bus              |
| ERR              | Xanh/Đỏ | Chẩn đoán mô-đun            |
| LINK/ACT IN, OUT | Xanh    | Trạng thái mạng             |
| 1..8 AB          | Xanh/Đỏ | Trạng thái vào/ra / IO-Link |

### 4.3 Sơ đồ chân đầu nối (mô-đun 8IOL)

**Cổng I/O A-code (đầu cái), M12 5 chân:**

| Chân | Tín hiệu | Chức năng                                        |
| ---- | -------- | ------------------------------------------------ |
| 1    | +24V     | Cấp nguồn +24V cho IO-Link hoặc cảm biến         |
| 2    | DIB/DOB  | Kênh B: ngõ vào hoặc ngõ ra số                   |
| 3    | GND/0V   | GND cấp nguồn cho IO-Link hoặc cảm biến          |
| 4    | C/Q      | Dữ liệu truyền thông IO-Link; Ch.A: Input/Output |
| 5    | FE (PE)  | n.c. (không nối)                                 |

**Cổng bus D-code (đầu cái), M12 5 chân:** 1 TD+ (tín hiệu vi sai truyền, dương); 2 RD+ (nhận, dương); 3 TD- (truyền, âm); 4 RD- (nhận, âm); 5 NC (trống).

**Cổng nguồn 7/8" 5 chân:**

| Chân | Tín hiệu | Chức năng                       |
| ---- | -------- | ------------------------------- |
| 1    | GND UL   | GND nguồn cơ cấu chấp hành      |
| 2    | GND US   | GND nguồn hệ thống và cảm biến  |
| 3    | FE (PE)  | Nối đất                         |
| 4    | +24V US  | +24V nguồn hệ thống và cảm biến |
| 5    | +24V UL  | +24V nguồn cơ cấu chấp hành     |

### 4.4 UR67-PN-78-16DIO-12-P

Mô-đun IO phân tán cho mạng PROFINET. 8 giao diện tín hiệu (M12, 5 cực, A-code), 2 giao diện truyền thông (M12, 4 cực, D-code), 2 giao diện nguồn (7/8", 5 cực). Mô-đun có 16 kênh vào/ra số, chức năng kênh cấu hình bằng phần mềm.

| Đèn             | Màu       | Mô tả                                                                    |
| --------------- | --------- | ------------------------------------------------------------------------ |
| **US**          | Xanh/Đỏ   | Trạng thái nguồn hệ thống và cảm biến (xanh = bình thường, đỏ = thấp áp) |
| **UL**          | Xanh/Đỏ   | Trạng thái nguồn cơ cấu chấp hành (xanh = bình thường, đỏ = thấp áp)     |
| BF              | Xanh/Đỏ   | Trạng thái bus                                                           |
| ERR             | Xanh/Đỏ   | Chẩn đoán mô-đun                                                         |
| DIA             | Xanh/Đỏ   | Chẩn đoán mô-đun                                                         |
| LINK/ACT P1, P2 | Xanh/Vàng | Trạng thái mạng                                                          |
| 1..8 AB         | Xanh/Đỏ   | Trạng thái vào/ra                                                        |

### 4.5 UR67-EC-78-16DIO-12-P

Tương tự mục 4.4 nhưng cho mạng EtherCAT. Đèn: US, UL, RUN, ERR, LINK/ACT (IN, OUT), 1..8 AB với ý nghĩa như các mục trên.

### 4.6 Sơ đồ chân đầu nối (mô-đun 16DIO)

**Cổng I/O A-code (đầu cái), M12 5 chân:**

| Chân | Tín hiệu | Chức năng                 |
| ---- | -------- | ------------------------- |
| 1    | +24V     | Cấp nguồn cảm biến +24V   |
| 2    | DIB/DOB  | Kênh B: vào hoặc ra       |
| 3    | GND/0V   | GND/0V cấp nguồn cảm biến |
| 4    | DIA/DOA  | Kênh A: vào hoặc ra       |
| 5    | FE (PE)  | Nối đất                   |

Cổng bus D-code và cổng nguồn 7/8" giống mục 4.3 (chân 1 GND UL; 2 GND US; 3 FE; 4 +24V US; 5 +24V UL).

### 4.7 UR67-IOL-H-16DIO-12-P

Mô-đun mở rộng IO-Link. 8 giao diện tín hiệu (M12, 5 chân, A-code), 1 giao diện IO-Link (M12, 5 chân, A-code), 16 kênh vào/ra số, cấu hình bằng phần mềm.

| Đèn     | Màu     | Mô tả                           |
| ------- | ------- | ------------------------------- |
| PWR     | Xanh/Đỏ | Trạng thái nguồn hệ thống       |
| COM     | Xanh    | Trạng thái truyền thông IO-Link |
| DIA     | Xanh/Đỏ | Chẩn đoán mô-đun                |
| 1..8 AB | Xanh/Đỏ | Trạng thái vào/ra               |

### 4.8 Sơ đồ chân (UR67-IOL-H-16DIO-12-P)

**Cổng IO-Link HUB A-code (đầu đực):** 1 +24V (nguồn); 2 NC; 3 GND/0V; 4 C/Q (cổng dữ liệu IO-Link); 5 FE (PE).
**Cổng I/O A-code (đầu cái):** 1 +24V (nguồn cảm biến); 2 DIB/DOB (kênh B); 3 GND/0V; 4 DIA/DOA (kênh A); 5 FE (PE).

### 4.9 Quan hệ byte và chân trong file IODD

| Loại        | Byte | bit 0        | 1            | 2            | 3            | 4            | 5            | 6            | 7            |
| ----------- | ---- | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| Dữ liệu vào | 0    | Chân 4 Port1 | Chân 2 Port1 | Chân 4 Port2 | Chân 2 Port2 | Chân 4 Port3 | Chân 2 Port3 | Chân 4 Port4 | Chân 2 Port4 |
| Dữ liệu vào | 1    | Chân 4 Port5 | Chân 2 Port5 | Chân 4 Port6 | Chân 2 Port6 | Chân 4 Port7 | Chân 2 Port7 | Chân 4 Port8 | Chân 2 Port8 |
| Dữ liệu ra  | 0    | Chân 4 Port1 | Chân 2 Port1 | Chân 4 Port2 | Chân 2 Port2 | Chân 4 Port3 | Chân 2 Port3 | Chân 4 Port4 | Chân 2 Port4 |
| Dữ liệu ra  | 1    | Chân 4 Port5 | Chân 2 Port5 | Chân 4 Port6 | Chân 2 Port6 | Chân 4 Port7 | Chân 2 Port7 | Chân 4 Port8 | Chân 2 Port8 |

(Bảng này ghi trong mục UR67-IOL-H; với mô-đun PN/EC 16DIO nên đối chiếu thêm GSDML/ESI để chắc chắn.)

### 4.10 Thông số kỹ thuật

#### 4.10.1 UR67-PN-78-8IOL-12-P và UR67-PN-78-16DIO-12-P – Hệ thống bus

| Mục                       | Giá trị                                                                                 |
| ------------------------- | --------------------------------------------------------------------------------------- |
| Giao thức                 | PROFINET                                                                                |
| Vendor ID                 | 0x0134                                                                                  |
| Device ID                 | 0x18C6                                                                                  |
| File GSDML                | GSDML-Vx.x-UR67-PN-78-8IOL-12-P-x.x.x.xml; GSDML-Vx.x-UR67-PN-78-16DIO-12-P-x.x.x.x.xml |
| Tốc độ truyền             | 100 Mbps song công toàn phần                                                            |
| Loại truyền               | Cổng điện 100 Mbps                                                                      |
| Tự thích ứng              | Hỗ trợ                                                                                  |
| Giao thức Ethernet hỗ trợ | DHCP, LLDP, DCP, SNMP, MRP                                                              |
| Chức năng switch          | Tích hợp 2 cổng switch, hỗ trợ RT và IRT                                                |
| Đầu nối                   | M12 D-code 4 chân                                                                       |

#### 4.10.2 UR67-EC-78-8IOL-12-P và UR67-EC-78-16DIO-12-P – Hệ thống bus

| Mục                           | Giá trị                                 |
| ----------------------------- | --------------------------------------- |
| Giao thức                     | EtherCAT                                |
| Vendor ID                     | 0x00000230                              |
| Product code                  | 0x0004B1A8 (8IOL); 0x0004B1AA (16DIO)   |
| File ESI                      | UR67-EC-78-16DIO-12-P-Vx.x-xxxxxxxx.xml |
| Tốc độ                        | 100 Mbps song công toàn phần            |
| Định địa chỉ (EtherCAT)       | Tự tăng, địa chỉ cố định                |
| Chu kỳ truyền thông tối thiểu | 500 µs                                  |
| Đầu nối                       | M12 D-code 4 chân                       |

**Ngõ vào số**

| Mục                  | Giá trị                         |
| -------------------- | ------------------------------- |
| Loại ngõ vào         | PNP                             |
| Chuẩn                | Type 3 IEC 61131-2              |
| Điện áp vào định mức | 24 V DC                         |
| Dòng vào (24 V DC)   | Điển hình 5 mA                  |
| Bảo vệ ngắn mạch     | Bảo vệ ngắn mạch nguồn cảm biến |
| Chỉ thị trạng thái   | Có (A xanh, B xanh)             |
| Chỉ thị chẩn đoán    | Có (đỏ nhấp nháy)               |
| Đầu nối              | M12 5 chân A-code               |

**Ngõ ra số**

| Mục                      | Giá trị                             |
| ------------------------ | ----------------------------------- |
| Loại ngõ ra              | PNP                                 |
| Chuẩn                    | Điển hình 2 A mỗi kênh, IEC 61131-2 |
| Dòng ra khi ở mức "1"    | Tối đa 2 A                          |
| Dòng ra khi ở mức "0"    | Tối đa 1 mA                         |
| Điện áp ra khi ở mức "1" | Tối thiểu UL − 2 V                  |
| Điện áp ra khi ở mức "0" | Tối đa 1 V                          |
| Dòng ra của mô-đun       | 12 A                                |
| Bảo vệ ngắn mạch         | Có (bảo vệ nhiệt)                   |
| Bảo vệ quá tải           | Có                                  |
| Chỉ thị trạng thái       | Có (A xanh, B xanh)                 |
| Chỉ thị chẩn đoán        | Có (đỏ sáng liên tục)               |
| Đầu nối                  | M12 5 chân A-code                   |

**Nguồn hệ thống / cảm biến (US)**

| Mục                      | Giá trị                               |
| ------------------------ | ------------------------------------- |
| Điện áp định mức         | 24 V DC (SELV/PELV)                   |
| Dải điện áp              | 24 V DC ± 25%                         |
| Khả năng mang dòng       | 12 A                                  |
| Dòng làm việc của mô-đun | 150 mA tại 24 V                       |
| Điện áp cấp cảm biến     | US                                    |
| Khả năng cấp cảm biến    | 12 A                                  |
| Bảo vệ đảo cực           | Có                                    |
| Đèn US                   | Có (xanh = bình thường, đỏ = thấp áp) |
| Đầu nối                  | Ổ cắm 7/8" 5 chân (nguồn)             |

**Nguồn cơ cấu chấp hành (UL)**

| Mục                     | Giá trị                               |
| ----------------------- | ------------------------------------- |
| Điện áp định mức UL     | 24 V DC (SELV/PELV)                   |
| Dải điện áp             | 24 V DC ± 25%                         |
| Khả năng mang dòng      | 12 A                                  |
| Ngưỡng thấp áp          | 18 V                                  |
| Độ trễ kiểm tra thấp áp | > 10 ms                               |
| Bảo vệ đảo cực          | **Không có**                          |
| Đèn nguồn               | Có (xanh = bình thường, đỏ = thấp áp) |
| Đầu nối                 | M12 5 chân A-code                     |

**Thông số chung**

| Mục                          | Giá trị                                                                                 |
| ---------------------------- | --------------------------------------------------------------------------------------- |
| Cấp bảo vệ                   | IP67 (khi lắp đúng)                                                                     |
| Nhiệt độ làm việc            | −40 °C đến +70 °C                                                                       |
| Độ ẩm làm việc               | 5…95%                                                                                   |
| Khối lượng                   | 540 g (các model 8IOL và 16DIO, PN và EC)                                               |
| Vật liệu vỏ                  | PBT + GF30                                                                              |
| Rung                         | 1 mm / 5–61,6 Hz; 15 g / 61,6–500 Hz                                                    |
| Va đập                       | 50 g / 11 ms                                                                            |
| Mô-men xiết                  | Đầu nối M12: 0,6 Nm; đầu nối 7/8": 0,8 Nm; điểm nối đất: 0,5 Nm; vít cố định M4: 0,5 Nm |
| Chứng nhận và tiêu chuẩn EMC | EN 55011:2016+A2:2021; EN IEC 61000-6-4:2019; EN IEC 61000-6-2:2019                     |

#### 4.10.3 UR67-IOL-H-16DIO-12-P

- Ngõ vào số: PNP, Type 3 IEC 61131-2, 24 V DC, 5 mA điển hình, bảo vệ ngắn mạch nguồn cảm biến, có đèn trạng thái (A xanh, B xanh) và chẩn đoán (đỏ).
- Ngõ ra số: PNP, điển hình 0,5 A mỗi kênh (IEC 61131-2 Type 1), tối đa 0,5 A ở mức "1", 1 mA ở mức "0"; điện áp ra mức "1" tối thiểu UL − 2 V, mức "0" tối đa 1 V; dòng ra mô-đun 4 A; có bảo vệ nhiệt và quá tải.
- Nguồn hệ thống/cảm biến: 24 V DC (SELV/PELV) ± 25%, mang dòng 4 A, dòng làm việc 50 mA tại 24 V, không bảo vệ đảo cực, đèn US xanh = bình thường, đỏ = thấp áp; đầu nối M12 IO-Link 5 chân A-code.
- Nguồn cơ cấu chấp hành: độ trễ kiểm tra thấp áp 1 ms, không bảo vệ đảo cực, có đèn nguồn.
- Thông số chung: IP67, −40…+70 °C, 5…95% ẩm, nặng 370 g, vỏ PBT+GF30, rung/va đập/mô-men xiết/EMC như trên.

#### 4.10.4 Phụ kiện – Chỉ mục tham số có thể sửa của UR67-IOL-H-16DIO-12-P

| Loại            | Mục cấu hình                                               | Index         | Định nghĩa                                              |
| --------------- | ---------------------------------------------------------- | ------------- | ------------------------------------------------------- |
| Giám sát mô-đun | Ngắn mạch/quá tải nguồn cảm biến; ngắn mạch/quá tải ngõ ra | 0x44 Sub 1    | 0x00 = Không kích hoạt; 0xFF = Kích hoạt (mặc định)     |
| Giám sát mô-đun | Thấp áp nguồn hệ thống/cảm biến; thấp áp nguồn ngõ ra      | 0x44 Sub 2    | 0x00 = Không kích hoạt; 0xFF = Kích hoạt (mặc định)     |
| Mô-đun          | Hành vi sau ngắn mạch/quá tải (chỉ ngõ ra số)              | 0x45 Sub 0    | 0 = Giữ tắt; 1 = Tự phục hồi (mặc định)                 |
| Mô-đun vào/ra   | Chống rung tín hiệu ngõ vào số                             | 0x46 Sub 0    | 0 = 0,1 ms; 1 = 3 ms (mặc định); 2 = 10 ms; 3 = 20 ms   |
| Mô-đun          | Kéo dài tín hiệu ngõ vào số                                | 0x47 Sub 0    | 0 = 0,5 ms; 1 = 15 ms (mặc định); 2 = 50 ms; 3 = 100 ms |
| Kênh            | **Cấu hình vào/ra** (2 byte)                               | 0x48 Sub 0    | 0 = Ngõ ra (Output); 1 = Ngõ vào (Input) (mặc định)     |
| Kênh            | Cấu hình vào/ra (1 byte, từng kênh)                        | 0x48 Sub 0~16 | 0 = Ngõ ra; 255 = Ngõ vào                               |
| Kênh            | Cho phép kéo dài tín hiệu                                  | 0x49 Sub 0    | 0 = Tắt (mặc định); 1 = Bật                             |
| Kênh            | Cài đặt FailSafe – chế độ lỗi                              | 0x4A Sub 0    | 0 = Giữ trạng thái cuối (mặc định); 1 = Trạng thái lỗi  |
| Kênh            | Cài đặt FailSafe – trạng thái lỗi                          | 0x4B Sub 0    | 0 = Reset ngõ ra (mặc định); 1 = Set ngõ ra             |
| Kênh            | Cài đặt thường mở/thường đóng (chế độ ngõ vào)             | 0x4C Sub 0    | 0 = NC; 1 = NO (mặc định)                               |

> **Quan trọng:** trong bảng này, mặc định của cấu hình vào/ra là **1 = Ngõ vào (Input)**. Với mô-đun IO-Link hub, mỗi kênh phải được đặt là Output (0) thì mới xuất được. Bảng này thuộc UR67-IOL-H; với UR67-PN-78-16DIO cần kiểm tra thêm trong GSDML hoặc trang cấu hình của mô-đun.

---

## 5. An toàn khi lắp đặt

**Cảnh báo – Nguy cơ điện giật!** Các công việc lắp đặt, đấu dây phải thực hiện sau khi cắt toàn bộ nguồn. Bảo đảm bệ lắp đã mất điện rồi mới làm việc.

**Chú ý – Nguy hiểm nhiệt độ cao!** Mô-đun có thể nóng khi vận hành. Trước khi chạm vào, bảo đảm nhiệt độ mô-đun đã hạ về mức bình thường.

### 5.1 Chuẩn bị trước khi lắp

- Lắp và vận hành thiết bị trong môi trường đáp ứng yêu cầu thiết kế.
- **Vị trí và kích thước lắp**: mô-đun phải lắp trên mặt phẳng ngang. Kích thước lắp và mô-men xiết của chi tiết cố định có ở các mục sau.
- **Mở hộp, kiểm tra hàng**: kiểm tra hàng giao đủ không và có hư hỏng khi vận chuyển không. Nếu có hư hỏng khi vận chuyển, báo ngay cho đơn vị vận chuyển tương ứng. Kiểm đếm tất cả bộ phận trong gói. Xử lý vật liệu đóng gói theo luật địa phương; bao bì carton có thể tái chế giấy.
- **Chú ý**: mô-đun có thể bị hỏng do tĩnh điện. Bảo đảm người vận hành và thiết bị đều được nối đất tốt.

### 5.2 Lắp đặt và nối đất

- Khoan lỗ phù hợp trên tấm lắp (kích thước lỗ xem phần kích thước lắp đặt).
- Mỗi mô-đun phải cố định bằng hai vít cố định và vòng đệm đi kèm (dùng chi tiết xiết theo DIN EN ISO 7089).
- Mô-men xiết: đầu cắm M12: 0,6 Nm; đầu cắm 7/8": 0,8 Nm.
- Mô-đun có một đầu nối đất để xả tĩnh điện và tăng khả năng chống nhiễu EMC. Điểm nối (FE) phải được nối với đất qua mạch có trở kháng thấp.
- Nếu vị trí lắp mô-đun không nối với đất, phải nối đất bằng dây tiếp địa dạng bện hoặc dây cáp đáng tin cậy.

### Kích thước lắp đặt

Trang 26: tham khảo kích thước lắp UR67-PN-78-8IOL-12, UR67-EC-78-8IOL-12, UR67-PN-78-16DIO-12, UR67-EC-78-16DIO-12. Trang 27: kích thước lắp UR67-IOL-H-16DIO-12. (Chỉ có bản vẽ.)
