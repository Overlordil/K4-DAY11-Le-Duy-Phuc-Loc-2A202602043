# QA review · B2-center

Mã khóa: 0ED9-9724

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_062370.jpg | L5 | R02 | Box `ThreeWheeler` và polygon cùng vùng vật thể chưa được ghép bằng `group_id`; kiểm tra lại cặp box/polygon trên ảnh gốc theo hướng dẫn K12. |
| adasind_117120.jpg | L1+L8 | R02 | Hai box `Pedestrian` chồng nhau ở cùng khu vực; kiểm tra trên ảnh gốc xem là hai người tách biệt hay box chưa bám đúng phần nhìn thấy. |
| adasind_117120.jpg | L2+L3 | R02 | Hai box `Car` chồng mép; kiểm tra ảnh gốc để xác nhận có hai xe riêng và mỗi box chỉ bao phần nhìn thấy của một xe. |

Ghi finding r2_qa: cell=L_only, rule_id có giá trị, why để trống.
