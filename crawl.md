- Khi crawl thì cần chú ý 2 vấn đề là proxy ( Vì thường các site hay chặn khi request số lượng lớn ) và tốc độ để crawl.
	- Proxy :	
		- Cách 1 : Sử dụng tor để làm proxy cho site
		Ưu điểm : Miễn phí , đơn giản, dễ làm và có nhiều ip 
		Nhược điểm:  tốn tài nguyên hệ thống và tốc độ của proxy chậm.
		Script để tạo nhiều proxy bằng tor. https://github.com/trimstray/multitor
		- Cách 2 : Sử dụng vultr để tạo ip-v6
		Ưu điểm : Có lượng lớn ip-v6  không giới hạn, giá thành rẻ ( 1 vps 5$ có thể tạo 2000 proxy), sử dụng xong có thể reset để được cấp thêm, có thể sử dụng lâu dài.
		Nhược điểm: Hiện nay có khá ít site chấp nhận cho ip-v6 request đến (Link top 500 site theo alexa test ip-v6 http://www.delong.com/ipv6_alexa500.html).
	- Crawl:
		- Hiện nay team đang sử dụng 2 cách chính là http request và selenium.
		- Sử dụng thử viện laravel để crawl.
		- Crawl với các site là Amazon, Ebay, Pinterest, Esty.
			- Amazon, Ebay, Esty sử dụng chủ yếu là http request. để request đến các site và xử html của trang để lấy ra thông tin
			- Pinterest thông qua việc debug browser tìm được api để lấy được data của pinterest thông qua json ( Hiện tại đang ko bị chặn). (Tham khảo link github : https://github.com/seregazhuk/php-pinterest-bot)
		- Tăng tốc độ crawl :
			- Sử dụng nhiều vps con để tăng tốc độ ( vì nếu 1 vps to khi thực hiện nhiều request sẽ bị hạn chế về băng thông mạng, dễ bị chặn khi request đến 1 site). 1 vps 5$ trong 10p có thể request đc 100k url.
			- Hạn chế giới hạn về phần cứng của 1 vps. ( tốc độ ổ cứng).