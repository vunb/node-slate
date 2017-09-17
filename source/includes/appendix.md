Phụ lục
=======

## <a name="pos_tags"></a>Bảng nhãn dán từ loại

| STT 	| Nhãn 	| Loại 	| Viết tắt của 	| Tên 	| Nhãn Universal Dependency 	| Ví dụ 	|
|-----	|------	|------	|----------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|---------------------------	|-----------------------------------------------------------------------------------------------------	|
| 1 	| N 	| 1 	| Noun 	| Danh từ 	| NOUN 	| tiếng, nước, thủ đô, nhân dân, đồ đạc, cây cối, chim muông 	|
| 3 	| Nc 	| 1 	| Noun Category 	| Danh từ chỉ loại 	| NOUN 	| con, cái, đứa, bức, chiếc 	|
| 5 	| Ni 	| 1 	|  	| Danh từ ký hiệu 	| NOUN 	| A1, A4, 60A, 60B, 20a, 20b, ABC, ABCD 	|
| 2 	| Np 	| 1 	| Proper Noun 	| Danh từ riêng 	| NOUN 	| Nguyễn Du, Việt Nam, Hải Phòng, Trường Đại học Bách khoa Hà Nội, Mộc tinh, Hoả tinh, Phật, Đạo Phật 	|
| 4 	| Nu 	| 1 	| Noun Unit 	| Danh từ đơn vị 	| NOUN 	| mét, cân, giờ, nắm, nhúm, hào, xu, đồng 	|
| 7 	| A 	| 2 	| Adjective 	| Tính từ 	| ADJ 	| tốt, xấu, đẹp; cao, thấp, rộng 	|
| 6 	| V 	| 3 	| Verb 	| Động từ 	| VERB 	| ngủ, ngồi, cười; đọc, viết, đá, đặt; thích, yêu, ghét, giống, muốn 	|
| 8 	| P 	| 4 	| Proper 	| Đại từ 	| PROPN 	| tôi, chúng tôi, hắn, nó, y, đại nhân, đại ca, huynh, đệ 	|
| 12 	| E 	| 5 	| Adposition (bao gồm prepositions và postpositions) 	| Giới từ 	| ADP 	| trên, dưới, trong, ngoài; của, trừ, ngoài, khỏi, ở 	|
| 15 	| I 	| 5 	| Interjection 	| Thán từ 	| INTJ 	| ôi, chao, a ha 	|
| 9 	| L 	| 5 	| Determiner 	| Định từ 	| DET 	| mỗi, từng, mọi, cái; các, những, mấy 	|
| 10 	| M 	| 5 	| Numeral 	| Số từ 	| NUM 	| một, mười, mười ba; dăm, vài, mươi; nửa, rưỡi 	|
| 16 	| T 	| 7 	| particle 	| Trợ từ, tình thái từ (tiểu từ) 	| PART 	| à, a, á, ạ, ấy, chắc, chăng, cho, chứ 	|
| 20 	| Z 	| 8 	| other 	| Yếu tố cấu tạo từ 	| X 	| bất, vô, phi 	|
| 11 	| R 	| 8 	|  	| Phó từ (Trạng từ) 	| X 	| đã, sẽ, đang, vừa, mới, từng, xong, rồi; rất, hơi, khí, quá 	|
| 19 	| X 	| 8 	| other 	| Các từ không phân loại được 	| X 	| ra sao, chừng như, thì ra 	|
| 13 	| C 	| 9 	| coordinating conjunction 	| Liên từ (thường là chính phụ) 	| CCONJ 	|  	|
| 14 	| Cc 	| 9 	| subordinating conjunction 	| Liên từ đẳng lập 	| SCONJ 	| và, hoặc, với, cùng 	|
| 21 	| CH 	| 10 	|  	| Nhãn dành cho các loại dấu (nhiều nhất là dấu câu) và một số ký hiệu khác 	| PUNCT 	| . ! ? , ; : 	|
| 17 	| b 	| 100 	| borrow 	| Từ tiếng nước ngoài (hay từ vay mượn). Khi gán nhãn ngữ liệu, nhãn từ tiếng nước ngoài thường là nhãn kép. Chẳng hạn nếu từ là chat thì nhãn của nó là Vb, video thì nhãn là Nb. Qua thống kê trong kho ngữ liệu thấy có: Ab Cb Eb Mb Nb Pb Vb. 	| _ 	| Internet, email, video, chat 	|
| 18 	| y 	| 100 	|  	| Từ viết tắt. Khi gán nhãn ngữ liệu, nhãn từ viết tắt thường là nhãn kép. Chẳng hạn nếu từ viết tắt là HIV thì nhãn của nó là Ny vì HIV viết đầy đủ thì là cụm danh từ. Qua thống kê trong kho ngữ liệu thấy có: Ny, Vy, Xy. 	| _ 	| OPEC, WTO, HIV, SN 	|                                                                         	|

Tham khảo:

* [Universal POS tags, universaldependencies.org][4]
* [Penn English Treebank POS tags][6]
* [Bảng tổng hợp nhãn dán và thử nghiệm][1]

## <a name="qtype_labels"></a>Bảng phân loại câu hỏi

| STT 	| Class 	| Definition 	| Diễn tả 	| Ví dụ 	|
|-----	|--------------	|---------------------------------------------	|----------------------------------------------	|-------------------------------------	|
|  	|  	|  	|  	|  	|
| 1 	| ABBREVIATION 	| abbreviation 	| viết tắt 	| ABBR 	|
| 2 	| abb 	| abbreviation 	| viết tắt 	| Hà Nội viết tắt là gì 	|
| 3 	| exp 	| expression abbreviated 	| diễn tả về cách viết tắt 	| NLP viết tắt của từ gì ? SOA là gì? 	|
| 4 	| ENTITY 	| entities 	| các thực thể 	|  	|
| 5 	| animal 	| animals 	| động vật 	|  	|
| 6 	| body 	| organs of body 	| các cơ quan của cơ thể 	|  	|
| 7 	| color 	| colors 	| màu sắc 	|  	|
| 8 	| creative 	| inventions, books and other creative pieces 	| sáng chế, sách và các tác phẩm sáng tạo khác 	|  	|
| 9 	| currency 	| currency names 	| tên tiền tệ 	|  	|
| 10 	| dis.med. 	| diseases and medicine 	| bệnh tật và thuốc men 	|  	|
| 11 	| event 	| events 	| sự kiện 	|  	|
| 12 	| food 	| food 	| món ăn 	|  	|
| 13 	| instrument 	| musical instrument 	| nhạc cụ 	|  	|
| 14 	| lang 	| languages 	| ngôn ngữ 	|  	|
| 15 	| letter 	| letters like a-z 	| chữ cái như a-z 	|  	|
| 16 	| other 	| other entities 	| các thực thể khác 	|  	|
| 17 	| plant 	| plants 	| cây cối 	|  	|
| 18 	| product 	| products 	| các sản phẩm 	|  	|
| 19 	| religion 	| religions 	| tôn giáo 	|  	|
| 20 	| sport 	| sports 	| các môn thể thao 	|  	|
| 21 	| substance 	| elements and substances 	| yếu tố và vật chất 	|  	|
| 22 	| symbol 	| symbols and signs 	| biểu tượng và dấu hiệu 	|  	|
| 23 	| technique 	| techniques and methods 	| kỹ thuật và phương pháp 	|  	|
| 24 	| term 	| equivalent terms 	| các điều khoản tương đương 	|  	|
| 25 	| vehicle 	| vehicles 	| xe cộ, phương tiện đi lại 	|  	|
| 26 	| word 	| words with a special property 	| những từ với một tài sản đặc biệt 	|  	|
| 27 	| DESCRIPTION 	| description and abstract concepts 	| mô tả và các khái niệm trừu tượng 	|  	|
| 28 	| definition 	| definition of sth. 	| định nghĩa của một thứ gì đó (sth.) 	|  	|
| 29 	| description 	| description of sth. 	| mô tả về thứ gì đó (sth.) 	|  	|
| 30 	| manner 	| manner of an action 	| cách hành động, cư xử 	|  	|
| 31 	| reason 	| reasons 	| lý do 	|  	|
| 32 	| HUMAN 	| human beings 	| con người 	|  	|
| 33 	| group 	| a group or organization of persons 	| nhóm hoặc tổ chức người 	|  	|
| 34 	| ind 	| an individual 	| một cá nhân 	|  	|
| 35 	| title 	| title of a person 	| chức danh của một người 	|  	|
| 36 	| description 	| description of a person 	| mô tả về một người 	|  	|
| 37 	| LOCATION 	| locations 	| vị trí 	|  	|
| 38 	| city 	| cities 	| các thành phố 	|  	|
| 39 	| country 	| countries 	| quốc gia 	|  	|
| 40 	| mountain 	| mountains 	| các ngọn núi, đồi 	|  	|
| 41 	| other 	| other locations 	| các địa điểm khác 	|  	|
| 42 	| state 	| states 	| tiểu bang 	|  	|
| 43 	| NUMERIC 	| numeric values 	| giá trị số 	|  	|
| 44 	| code 	| postcodes or other codes 	| mã bưu điện hoặc các mã khác 	|  	|
| 45 	| count 	| number of sth. 	| số lượng sth. 	|  	|
| 46 	| date 	| dates 	| ngày tháng 	|  	|
| 47 	| distance 	| linear measures 	| khoảng cách, các phép đo tuyến tính 	|  	|
| 48 	| money 	| prices 	| giá cả 	|  	|
| 49 	| order 	| ranks 	| xếp hạng 	|  	|
| 50 	| other 	| other numbers 	| số khác 	|  	|
| 51 	| period 	| the lasting time of sth. 	| chu kỳ, thời gian sống của một vật 	|  	|
| 52 	| percent 	| fractions 	| phân số 	|  	|
| 53 	| speed 	| speed 	| tốc độ 	|  	|
| 54 	| temp 	| temperature 	| nhiệt độ 	|  	|
| 55 	| size 	| size, area and volume 	| kích thước, diện tích và khối lượng 	|  	|
| 56 	| weight 	| weight 	| cân nặng 	|  	|

Tham khảo:

* [Definition of Question Classes, by Xin Li and Dan Roth][5]
* [Bảng tổng hợp nhãn dán và thử nghiệm][1]

<!-- References -->
[1]: https://docs.google.com/spreadsheets/d/12bqhU5NS9rxM9kY2pBjRSB6Av_XsoOonHEqiv-lDKZw/edit#gid=458521935
[2]: https://docs.google.com/spreadsheets/d/1VXHVyWU0Jnab62VQacNED8Sz43ofUSywFu21Y1ukYjE/edit#gid=458521935
[3]: http://www.tablesgenerator.com/markdown_tables
[4]: http://universaldependencies.org/u/pos/
[5]: http://cogcomp.org/Data/QA/QC/definition.html
[6]: http://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html
[7]: https://stackoverflow.com/a/1833718/1896897