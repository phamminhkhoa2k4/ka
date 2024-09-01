CREATE TABLE  CGTRINH (
	STT_CTR int NOT NULL ,
	TEN_CTR varchar (20)  NULL ,
	DIACHI_CTR varchar (20)  NULL ,
	TINH_THANH varchar (15)  NULL ,
	KINH_PHI int NULL ,
	TEN_CHU varchar (20)  NULL ,
	TEN_THAU varchar (20)  NULL ,
	NGAY_BD date NULL 
) ;


CREATE TABLE  CHUNHAN (
	TEN_CHU varchar (20)  NOT NULL ,
	DCHI_CHU varchar (20)  NULL 
) ;


CREATE TABLE  CHUTHAU (
	TEN_THAU varchar (20)  NOT NULL ,
	TEL char (7)  NULL ,
	DCHI_THAU varchar (20)  NULL 
) ;


CREATE TABLE  CONGNHAN (
	HOTEN_CN varchar (20)  NOT NULL ,
	NAMS_CN int NULL ,
	NAM_VAO_N int NULL ,
	CH_MON varchar (10)  NULL 
) ;


CREATE TABLE  KTRUCSU (
	HOTEN_KTS varchar (20)  NOT NULL ,
	NAMS_KTS int NULL ,
	PHAI char (2)  NULL ,
	NOI_TN varchar (15)  NULL ,
	DCHI_LL_KTS varchar (30)  NULL 
) ;


CREATE TABLE  THAMGIA (
	HOTEN_CN varchar (20)  NOT NULL ,
	STT_CTR int NOT NULL ,
	NGAY_TGIA date NULL ,
	SO_NGAY int NULL 
) ;


CREATE TABLE  THIETKE (
	HOTEN_KTS varchar (20)  NOT NULL ,
	STT_CTR int NOT NULL ,
	THU_LAO int NULL 
) ;


ALTER TABLE  CGTRINH ADD 
	CONSTRAINT PK_CGTRINH PRIMARY KEY  	(STT_CTR	)  ; 


ALTER TABLE  CHUNHAN ADD 
	CONSTRAINT PK_CHUNHAN PRIMARY KEY  (	TEN_CHU	)  ; 


ALTER TABLE  CHUTHAU ADD 
	CONSTRAINT PK_CHUTHAU PRIMARY KEY  (	TEN_THAU	)  ; 


ALTER TABLE  CONGNHAN ADD 
	CONSTRAINT PK_CONGNHAN PRIMARY KEY  (	HOTEN_CN	)  ; 


ALTER TABLE  KTRUCSU ADD 
	CONSTRAINT PK_KTRUCSU PRIMARY KEY  	(	HOTEN_KTS	)  ; 


ALTER TABLE  THAMGIA ADD 
	CONSTRAINT PK_THAMGIA PRIMARY KEY  	(	HOTEN_CN,	STT_CTR	)  ; 


ALTER TABLE  THIETKE ADD 
	CONSTRAINT PK_THIETKE PRIMARY KEY  	(	HOTEN_KTS,	STT_CTR	)  ; 


ALTER TABLE  CGTRINH ADD 
	CONSTRAINT FK_CGTRINH_CHUNHAN FOREIGN KEY 	(	TEN_CHU	) REFERENCES  CHUNHAN (	TEN_CHU	);

ALTER TABLE  CGTRINH ADD 
	CONSTRAINT FK_CGTRINH_CHUTHAU FOREIGN KEY 
	(	TEN_THAU	) REFERENCES  CHUTHAU (	TEN_THAU	);


ALTER TABLE  THAMGIA ADD 
	CONSTRAINT FK_THAMGIA_CGTRINH FOREIGN KEY 
	(		STT_CTR	) REFERENCES  CGTRINH (		STT_CTR	);

ALTER TABLE  THAMGIA ADD 
	CONSTRAINT FK_THAMGIA_CONGNHAN FOREIGN KEY 
	(		HOTEN_CN	) REFERENCES  CONGNHAN (		HOTEN_CN	);


ALTER TABLE  THIETKE ADD 
	CONSTRAINT FK_THIETKE_CGTRINH FOREIGN KEY 	(STT_CTR) REFERENCES  CGTRINH (	STT_CTR	);

ALTER TABLE  THIETKE ADD 
	CONSTRAINT FK_THIETKE_KTRUCSU FOREIGN KEY 
	(	HOTEN_KTS	) REFERENCES  KTRUCSU (	HOTEN_KTS );


insert into  chunhan values ('so t mai du lich','54 xo viet nghe tinh');
insert into  chunhan values ('so van hoa thong tin','101 hai ba trung');
insert into  chunhan values ('so giao duc','29 duong 3/2');
insert into  chunhan values ('dai hoc can tho','56 duong 30/4');
insert into  chunhan values ('cty bitis','29 phan dinh phung');
insert into  chunhan values ('nguyen thanh ha','45 de tham');
insert into  chunhan values ('phan thanh liem','48/6 huynh thuc khan');


insert into  chuthau values ('cty xd so 6','567456','5 phan chu trinh');
insert into  chuthau values ('phong dich vu so xd','206481','2 le van sy');
insert into  chuthau values ('le van son','028374','12 tran nhan ton');
insert into  chuthau values ('tran khai hoan','658432','20 nguyen thai hoc');

insert into  congnhan values ('nguyen thi suu',   45 ,    60  ,'ho');
insert into  congnhan values ('vi chi a',   66  ,    87  ,'han');
insert into  congnhan values ('le manh quoc',   56  ,    71 ,'moc');
insert into  congnhan values ('vo van chin',   40 ,    52  ,'son');
insert into  congnhan values ('le quyet thang',   54  ,    74 ,'son');
insert into  congnhan values ('nguyen hong van',   50  ,    70   ,'dien');
insert into  congnhan values ('dang van son',   48,    65 ,'dien');




insert into  ktrucsu values ('le thanh tung',   1956          ,'1','tp hcm','25 duong 3/2 tp bien hoa');
insert into  ktrucsu values ('le kim dung',   1952          ,'0','ha noi','18/5 phan van tri tp can tho');
insert into  ktrucsu values ('nguyen anh thu',   1970          ,'0','new york usa','khu i dhct tp can tho');
insert into  ktrucsu values ('nguyen song do quyen',   1970          ,'0','tp hcm','73 tran hung dao tp hcm');
insert into  ktrucsu values ('truong minh thai',   1950          ,'1','paris france','12/2/5 tran phu tp hanoi');

insert into  cgtrinh values 
( 1       ,'khach san quoc te','5 nguyen an ninh','can tho',450 ,'so t mai du lich','cty xd so 6','dec-13-1994'); 
insert into  cgtrinh values 
( 2       ,'cong vien thieu nhi','100 nguyen thai hoc','can tho',   200         ,'so van hoa thong tin','cty xd so 6','may-08-1994'); 
insert into  cgtrinh values 
( 3       ,'hoi cho nong nghiep','bai cat','vinh long',   1000        ,'so t mai du lich','phong dich vu so xd','jun-10-1994'); 
insert into  cgtrinh values 
( 4       ,'truong mg mang non','48 cm thang 8','can tho',   30          ,'so giao duc','le van son','jun-10-1994'); 
insert into  cgtrinh values 
( 5       ,'khoa trong trot dhct','khu ii dhct','can tho',   3000        ,'dai hoc can tho','le van son','jun-10-1994'); 
insert into  cgtrinh values 
( 6       ,'van phong bitis','25 phan dinh phung','ha noi',   40          ,'cty bitis','le van son','oct-05-1994'); 
insert into  cgtrinh values 
( 7       ,'nha rieng 1','124/5 nguyen trai','tp hcm',   65          ,'nguyen thanh ha','phong dich vu so xd','nov-15-1994'); 
insert into  cgtrinh values 
( 8       ,'nha rieng 2','76 chau van liem','ha noi',   100         ,'phan thanh liem','tran khai hoan','sep-06-1994'); 

insert into  thamgia values ('nguyen thi suu',   2       ,'may-08-1994',   20          );
insert into  thamgia values ('nguyen thi suu',   4       ,'sep-07-1994',   20          );
insert into  thamgia values ('nguyen thi suu',   1       ,'dec-15-1994',   5           );
insert into  thamgia values ('le manh quoc',   1       ,'dec-18-1994',   6           );
insert into  thamgia values ('vo van chin',   2       ,'may-10-1994',   10          );
insert into  thamgia values ('le quyet thang',   2       ,'may-12-1994',   5           );
insert into  thamgia values ('nguyen hong van',   1       ,'dec-16-1994',   7           );
insert into  thamgia values ('nguyen hong van',   4       ,'sep-14-1994',   7           );
insert into  thamgia values ('dang van son',   3       ,'jun-10-1994',   18          );
insert into  thamgia values ('vo van chin',   3       ,'jun-10-1994',   10          );



insert into  thietke values ('le thanh tung',   1       ,    25          );
insert into  thietke values ('le kim dung',   5       ,    30          );
insert into  thietke values ('truong minh thai',   8       ,    18          );
insert into  thietke values ('le kim dung',   6       ,    40          );
insert into  thietke values ('nguyen anh thu',   3       ,    12          );
insert into  thietke values ('le thanh tung',   7       ,    10          );
insert into  thietke values ('nguyen song do quyen',   2       ,    6           );
insert into  thietke values ('truong minh thai',   6       ,    27          );
insert into  thietke values ('le kim dung',   4       ,    20          );
insert into  thietke values ('truong minh thai',   1       ,    12          );




--2. M? các b?ng d? li?u ?? xem ki?u d? li?u c?a t?ng tr??ng và quan sát d? li?u c?a t?ng b?ng


SELECT* FROM cgtrinh;
SELECT* FROM chunhan;
SELECT* FROM chuthau;
SELECT* FROM congnhan;
SELECT* FROM ktrucsu;
SELECT* FROM thamgia;
SELECT* FROM thietke;


--3. Hăy cho bi?t thông tin v? các ki?n trúc s? có h? là Lê và sinh n?m 1956

SELECT *
FROM ktrucsu
WHERE hoten_kts LIKE 'le%' and nams_kts = 1956;   

--4. 4. Hăy cho bi?t tên các công tŕnh b?t ??u trong kho?ng 1/9/1994 ??n 20/10/1994

SELECT ten_ctr
FROM cgtrinh
where ngay_bd between to_date('1-9-1994','dd-mm-yyyy') and to_date('20-10-1994','dd-mm-yyyy');

--5. Hăy cho bi?t tên và ??a ch? các công tŕnh do ch? th?u ‘công ty xây d?ng s? 6’ thi 
--công (chú ư: xem d? li?u ?? l?y ?úng tên công ty xây d?ng s? 6)


SELECT  ten_ctr, diachi_ctr
FROM cgtrinh 
WHERE TEN_THAU ='cty xd so 6';

--6. T́m tên và ??a ch? liên l?c c?a các ch? th?u thi công công tŕnh ? C?n Th? do ki?n 
--trúc s? Lê Kim Dung thi?t k?


SELECT ct.ten_thau, ct.tel, ct.dchi_thau
FROM chuthau ct
join cgtrinh c on c.ten_thau = ct.ten_thau
join thietke t on t.stt_ctr = c.stt_ctr
WHERE c.tinh_thanh ='can tho' and  t.hoten_kts ='le kim dung';



select * from cgtrinh;



--7. Hăy cho bi?t n?i t?t nghi?p c?a các ki?n trúc s? ?ă thi?t k? công tŕnh Khách s?n qu?c t? ? C?n Th?


select kts.noi_tn
from cgtrinh ct
join thietke tk on  ct.stt_ctr = tk.stt_ctr
join ktrucsu kts on tk.hoten_kts = kts.hoten_kts
where ct.ten_ctr ='khach san quoc te' and ct.tinh_thanh ='can tho';



--8. Cho bi?t h? tên, n?m sinh và n?m vào ngh? c?a các công nhân có chuyên môn hàn
--ho?c ?i?n ?ă tham gia các công tŕnh mà ch? th?u Lê V?n S?n ?ă trúng th?u


select *
from congnhan cn
join thamgia tg on cn.hoten_cn = tg.hoten_cn
join cgtrinh ct on tg.stt_ctr = ct.stt_ctr
join chuthau cth on ct.ten_thau = cth.ten_thau
where  cth.ten_thau='le van son';


select *
from chuthau;


--9. Nh?ng công nhân nào ?ă b?t ??u tham gia công tŕnh Khách s?n Qu?c t? ? C?n Th? trong giai ?o?n t? ngày 15/12/1994 ??n 31/12/1994



select cn.hoten_cn
from congnhan cn
join thamgia tg on cn.hoten_cn = tg.hoten_cn
join cgtrinh ct on tg.stt_ctr = ct.stt_ctr
where  ct.ten_ctr = 'khach san quoc te' and ct.tinh_thanh ='can tho' and tg.ngay_tgia between to_date('15-12-1994','dd-mm-yyyy') and to_date('31-12-1994','dd-mm-yyyy');

select *
from cgtrinh;



--10. Cho bi?t h? tên và n?m sinh c?a các ki?n trúc s? ?ă t?t nghi?p ? TP HCM và ?ă thi?t
--k? ít nh?t m?t công tŕnh có kinh phí ??u t? trên 400 tri?u ??ng


select kts.hoten_kts, kts.nams_kts
from ktrucsu kts
join thietke tk on kts.hoten_kts = tk.hoten_kts
join cgtrinh ct on tk.stt_ctr = ct.stt_ctr
where tk.stt_ctr >=1 and kts.noi_tn ='tp hcm' and ct.kinh_phi > 400;




select *
from ktrucsu;


--11. T́m h? tên và chuyên môn c?a các công nhân tham gia các công tŕnh do ki?n trúc s? Lê Thanh Tùng thi?t k?

select cn.hoten_cn, cn.ch_mon
from congnhan cn
join thamgia tg on cn.hoten_cn = tg.hoten_cn
join thietke tk on tg.stt_ctr = tk.stt_ctr
where tk.hoten_kts ='le thanh tung';



--12. Cho bi?t tên công tŕnh có kinh phí cao nh?t

select max(kinh_phi)
from cgtrinh;


--13. Cho bi?t h? tên ki?n trúc s? tr? tu?i nh?t

select max(nams_kts)
from ktrucsu;

--14. T́m t?ng kinh phí c?a các công tŕnh theo t?ng ch? th?u

select ct.ten_thau, sum(kinh_phi)
from cgtrinh ct
group by ct.ten_thau;

--15. T́m tên và ??a ch? nh?ng ch? th?u ?ă trúng th?u công tŕnh có kinh phí th?p nh?t

select cth.ten_thau, cth.dchi_thau ,min(kinh_phi)
from chuthau cth
join cgtrinh ct on cth.ten_thau = ct.ten_thau
group by cth.ten_thau, cth.dchi_thau;


--16. Cho bi?t h? tên các ki?n trúc s? có t?ng thù lao thi?t k? các công tŕnh l?n h?n 25 tri?u


select kts.hoten_kts, sum(thu_lao) 
from ktrucsu kts
join thietke tk on kts.hoten_kts = tk.hoten_kts
join cgtrinh ct on tk.stt_ctr = ct.stt_ctr
group by kts.hoten_kts 
having sum(thu_lao) > 25;



select * from thietke;



--17. Cho bi?t s? l??ng các ki?n trúc s? có t?ng thù lao thi?t k? các công tŕnh l?n h?n 25 tri?u

select count(*) tong_kts
from(
select kts.hoten_kts, sum(thu_lao) 
from ktrucsu kts
join thietke tk on kts.hoten_kts = tk.hoten_kts
join cgtrinh ct on tk.stt_ctr = ct.stt_ctr
group by kts.hoten_kts 
having sum(thu_lao) > 25

);
--18. Tính s? công tŕnh mà m?i ki?n trúc s? ?ă thi?t k?

select count(ct.stt_ctr) so_cong_trinh, tk.hoten_kts 
from cgtrinh ct 
join thietke tk on ct.stt_ctr = tk.stt_ctr
group by tk.hoten_kts, ct.stt_ctr;


--19. Tính t?ng s? công nhân đ? tham gia m?i công tr?nh

select sum(tong)
from(
select tg.stt_ctr, tg.hoten_cn, count(tg.hoten_cn) tong
from thamgia tg 
group by tg.stt_ctr, tg.hoten_cn) ;

--20. T?m tên và đ?a ch? công tr?nh có t?ng s? công nhân tham gia nhi?u nh?t



select ct.ten_ctr, ct.diachi_ctr, count(hoten_cn) as tong_so_cn
from thamgia tg 
join cgtrinh ct on tg.stt_ctr = ct.stt_ctr
group by ct.ten_ctr,ct.diachi_ctr
order by tong_so_cn;


--21. Cho bi?t tên các thành ph? và kinh phí trung b?nh c?a các công tr?nh c?a t?ng thành 
--ph? tương ?ng


select ct.tinh_thanh, avg(kinh_phi)kinh_phi_tb
from cgtrinh ct 
group by ct.tinh_thanh
order by kinh_phi_tb
;





select * from thamgia;




Để tìm hiểu sự thông thương giữa các bảng trong cơ sở dữ liệu quản lý công trình, ta cần xác định các mối quan hệ giữa các bảng thông qua các khóa chính và khóa ngoại. Dưới đây là phân tích mối liên kết giữa các bảng:

KTRUCSU (HOTEN_KTS, NAMS_KTS, PHAI, NOI_TN, DCHI_LL_KTS):

Chức năng: Lưu thông tin về kiến trúc sư.
Mối quan hệ: Liên kết với bảng THIETKE thông qua cột HOTEN_KTS, là khóa chính của KTRUCSU.
CHUTHAU (TEN_THAU, TEL, DCHI_THAU):

Chức năng: Lưu thông tin về chủ thầu.
Mối quan hệ: Liên kết với bảng CGTRINH qua cột TEN_THAU, là khóa chính của CHUTHAU.
CHUNHAN (TEN_CHU, DCHI_CHU):

Chức năng: Lưu thông tin về chủ công trình.
Mối quan hệ: Liên kết với bảng CGTRINH qua cột TEN_CHU, là khóa chính của CHUNHAN.
CONGNHAN (HOTEN_CN, NAMS_CN, NAM_VAO_N, CH_MON):

Chức năng: Lưu thông tin về công nhân.
Mối quan hệ: Liên kết với bảng THAMGIA qua cột HOTEN_CN, là khóa chính của CONGNHAN.
CGTRINH (STT_CTR, TEN_CTR, DIACHI_CTR, TINH_THANH, KINH_PHI, TEN_CHU, TEN_THAU, NGAY_BD):

Chức năng: Lưu thông tin về các công trình.
Mối quan hệ:
Liên kết với CHUNHAN qua TEN_CHU.
Liên kết với CHUTHAU qua TEN_THAU.
Liên kết với THAMGIA qua STT_CTR.
Liên kết với THIETKE qua STT_CTR.
THAMGIA (HOTEN_CN, STT_CTR, NGAY_TGIA, SO_NGAY):

Chức năng: Lưu thông tin công nhân tham gia các công trình.
Mối quan hệ:
Liên kết với CONGNHAN qua HOTEN_CN.
Liên kết với CGTRINH qua STT_CTR.
THIETKE (HOTEN_KTS, STT_CTR, THU_LAO):

Chức năng: Lưu thông tin thiết kế công trình của các kiến trúc sư.
Mối quan hệ:
Liên kết với KTRUCSU qua HOTEN_KTS.
Liên kết với CGTRINH qua STT_CTR.
Tóm tắt sự thông thương giữa các bảng:
Bảng CGTRINH là trung tâm, kết nối với hầu hết các bảng khác.
KTRUCSU liên kết với THIETKE, sau đó liên kết với CGTRINH.
CONGNHAN liên kết với THAMGIA, sau đó liên kết với CGTRINH.
CHUTHAU và CHUNHAN liên kết trực tiếp với CGTRINH.


