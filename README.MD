<script type="text/javascript">
	$(function() {
		var $sidebar   = $(".adv"),
			$window    = $(window),
			offset     = $sidebar.offset(),
			offset2    = $(".content-main").offset(),
			topPadding = 15;
			
		var elem = $('.adv');
		var connect_main = $('.content-main');
		
		var ads_height = $('.right-main').height();
		if ($('.left-main').height() > ads_height){
			ads_height = $('.left-main').height();
		}

		$window.scroll(function() {
			if ($window.scrollTop() > offset.top){
				if (connect_main.outerHeight() + connect_main.offset().top > $window.scrollTop() + ads_height + 20){
					$sidebar.stop().animate({
						marginTop: $window.scrollTop() - offset.top + topPadding
					});		
				}
			}else{
				$sidebar.stop().animate({
					marginTop: 0
				});	
			}
		});
	});

</script>