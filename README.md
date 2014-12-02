codeigniter_pagination
======================

코드이그나이터 커스텀 페이징 입니다. 
위치는 application/libraries/ 밑에 넣어주시면 됩니다.
query 시 limit 부분은 (페이지번호 - 1) 해주셔야 됩니다.


#컨트롤러 단에서 설정
$param = array('total_rows'=>500,		// 총 게시물수 갯수
		'per_page'=>20,			// 한 페이지당 출력수
		'view_page'=>10,		// 한 화면에서 보이는 최대 페이지 수
		'page_position'=>2,		// list/page/3 일때 페이지 번호의 위치 (0 부터 시작)
		'use_end'=>TRUE			// 처음 페이지, 끝 페이지 사용여부 (기본 FALSE)
		);
$this->load->library('pagination_custom', $param);



#VIEW 단에서 출력
<?=$this->pagination_custom->create_links();?>





!검색 쿼리는 기존 코드이그나이터 주소체계인 /q/subject/ 가 아닌 제일 끝 주소에 /?q=subject 식으로 자동으로 붙습니다. 