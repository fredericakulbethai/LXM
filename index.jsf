<?php
header("Content-type: text/html; charset=utf-8");
define('SELF', pathinfo(__FILE__, PATHINFO_BASENAME));
define('FCPATH', str_replace("\\", "/", str_replace(SELF, '', __FILE__)));
require_once(FCPATH.'config.php');

if(!is_referer()){
exit(ERROR);
}
//—————————————————————————————————————————————————————————————————————
//
$url=$_GET['url'];
if($url==''){
    die('<html><meta name="robots" content="noarchive"><head><title>'.$user['title'].'</title></head><style>h1{color:white; text-align:center; font-family: Microsoft Jhenghei;}p{color:#f90; font-size: 1.2rem;text-align:center;font-family: Microsoft Jhenghei;}</style><body bgcolor="#000000"><table width="100%" height="100%" align="center"><td align="center">'.$user['cont'].'</table></body></html>');
}

?>
<!DOCTYPE html>
<html>
	<head>
		<meta http-equiv="Content-Type" content="text/html;charset=utf-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=11" />
		<meta content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no" id="viewport" name="viewport">
	</head>
	<title>
		<?php echo $user['title'] ?>
	</title>
	<style type="text/css">
		body,
		html,
		.content {
			background-color: black;
			padding: 0;
			margin: 0;
			width: 100%;
			height: 100%;
			color: #999;
		}

		@keyframes masked-animation {
			0% {
				background-position: 0 0;
			}

			100% {
				background-position: -100%, 0;
			}
		}
	</style>
	<script src="https://consumer-res.huawei.com/etc/designs/huawei-cbg-site/statics/jquery-3.4.1.js" type="text/javascript">
	</script>
	<link rel="stylesheet" href="DPlayer/DPlayer.min.css" type="text/css">
	<script type="text/javascript" src="DPlayer/DPlayer.min.js" charset="utf-8">
	</script>
	<script type="text/javascript" src="DPlayer/hls.min.js" charset="utf-8">
	</script>
	<link rel="stylesheet" href="Dmplayer/css/yzmplayer.css?111">
	<link rel="stylesheet" href="Dmplayer/css/dmplayer.css">

	<script src="Dmplayer/js/jquery.min.js"></script>
	<script src="Dmplayer/js/layer/layer.js"></script>
	<script src="Dmplayer/js/md5.min.js"></script>
	<script src="https://cdn.jsdelivr.net/npm/cdnbye@latest"></script>
	<script src="Dmplayer/js/yzmplayer.1.js?1"></script>
	<script src="Dmplayer/js/setting.js?1"></script>
	<script src="ckplayer/ckplayer.js?1"></script>
	<?php if($user['debug']==1){ ?>
	<script>
	    document.oncontextmenu = function () { return false; }
        document.onkeydown = function () {
        var e = window.event || arguments[0];
        if (e.keyCode == 123) {
            return false;
        } else if ((e.ctrlKey) && (e.shiftKey) && (e.keyCode == 73)) {
            return false;
        } else if ((e.shiftKey) && (e.keyCode == 121)) {
            return false;
        } else if ((e.ctrlKey) && (e.keyCode == 85)) {
            return false;
        }
    };
	</script>
	<?php } ?>
	<script type="text/javascript">
		var host = document.domain;
		var domain = '<?=fdhost?>';
		var url = '<?=$url?>';

		function player() {
			$.post("api.php", {
					"url": url
				},
				function(data) {
					if (data['code'] == 200) {
						new_url = data['url'];
						if (RegExp(/qq.com/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else if (RegExp(/baidu.com/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else if (RegExp(/ixigua.com/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else if (RegExp(/.iqiyi.com/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else if (RegExp(/.189.cn/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else if (RegExp(/gz.ctyunapi.cn/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else if (RegExp(/migu/).exec(new_url)) {
							$("head").append('<meta name="referrer" content="Origin"><meta name="referrer" content="never" />');
						} else {
							$("head").append('<meta name="referrer" content="Origin">');
						}
						var isiPad = navigator.userAgent.match(/iPad|iPhone|Linux|Android|iPod/i) != null;
						by = '<?php echo $user['
						byjx '] ?>';
						if (data['player'] == 'url') {
							$('#player').html(
								'<iframe width="100%" height="100%" allowTransparency="true" frameborder="0" scrolling="no" src="' + data[
									'url'] + '"><\/iframe>');
						} else if ((isiPad) && data['type'] != 'm3u8') {
							$('#player').html('<video controls="controls" width="100%" height="100%" poster="' + data[
								'img'] + '" autoplay = "autoplay"><source src="' + data['url'] + '" type="video/mp4"><\/source><\/video>');
						} else if (data['player'] == 'dmplayer') {
							autoplay = true;
							up = {
								"usernum": "1", //在线人数
								"mylink": "", //域名
							}
							config = {
								"api": '<?php echo $user["dmku"]; ?>',
								"danmakuinterval": 180,
								"url": data['url'], //视频链接
								"id": 'yunhai', //视频id
								"sid": "", //集数id
								"pic": '<?php echo $user['img'] ?>',
								"title": "", //视频标题
								"next": "", //下一集链接
								"user": '', //用户名
								"group": "",
								"logo": '<?php echo $user['logo'] ?>',
								"autoplay": '<?php echo $user['autoplay'] ?>',
							}
							dplayermenu = '<?php echo $user['bq'] ?>';
							if (dplayermenu) {
								config.contextmenu = [{
									text: dplayermenu.split(",")[0],
									link: dplayermenu.split(",")[1]
								}];
							}
							YZM.start();
						} else if (data['player'] == 'ckplayer') {
							$('#videoPause').click(function() {
								if (window.ckplayer1 != null) {
									window.ckplayer1.videoPlay();
									$(this).hide();
								}
							});

							function showPauseBtn() {
								$('#videoPause').show();
							}

							function hidePauseBtn() {
								$('#videoPause').hide();
							}

							function durationHandler() {
								showPauseBtn();
							}

							function onckplay() {
								hidePauseBtn();
							}

							function ckloadedHandler() {
								window.ckplayer1.addListener('duration', durationHandler); //监听元数据
								window.ckplayer1.addListener('play', onckplay);
							}

							function player() {
								var isMobile = navigator.userAgent.match(/iPad|iPhone|Android|Linux|iPod/i) != null;
								var autoplay = '<?php echo $user['autoplay']; ?>';

								if (typeof(window.ckplayer1) != "undefined" && window.ckplayer1 != null) {
									window.ckplayer1.videoPause();
									window.ckplayer1.videoClear();
								}

								var params = {
									container: '#player',
									variable: 'ckplayer1',
									mobileCkControls: false,
									mobileAutoFull: false,
									video: data['url'],
									poster: "<?php echo $user['img'];?>",
									html5m3u8: true,
									autoplay: autoplay,
									flashplayer: <?php echo intval($_GET['flash']);?> == 1 ? true : false,
								};

								<?php if($user['bq']){ $dcon = explode(',',$user['bq'])?>
								params.contextmenu = [
									["<?php echo $dcon[0];?>", 'link', "<?php echo $dcon[1];?>", '_blank']
								];
								<?php }?>

								<?php if($user['logo']){?>
								params.logo = "<img src=\"<?php echo $user['logo'];?>\" border=\"0\" />";
								<?php }?>

								params.loaded = 'ckloadedHandler';
								window.ckplayer1 = new ckplayer(params);

								if (autoplay) {
									window.ckplayer1.videoPlay();
								}

								$("#loading").hide();
								$("#player").show();
							}

							$(function() {
								player();
							});

						} else if (data['player'] == 'dplayer') {

							var webdata = {
								set: function(key, val) {
									window.sessionStorage.setItem(key, val);
								},
								get: function(key) {
									return window.sessionStorage.getItem(key);
								},
								del: function(key) {
									window.sessionStorage.removeItem(key);
								},
								clear: function(key) {
									window.sessionStorage.clear();
								}
							};
							var m3u8url = data['url']
							dp = new DPlayer({
								element: document.getElementById("player"),
								contextmenu: [{
									<?php if($user['bq']){
                                        $dcon = explode(',',$user['bq'])
                                    ?>
									text: '<?php echo $dcon[0] ?>',
									link: '<?php echo $dcon[1] ?>',
									<?php } ?>
								}, ],
								autoplay: '<?php echo $user['autoplay'] ?>',
								logo: '<?php echo $user['logo'] ?>',
								video: {
									quality: [{
										name: '普清',
										url: m3u8url
									}, {
										name: '超清',
										url: m3u8url
									}],
									defaultQuality: 1,
									pic: '<?php echo $user['img'] ?>',
								},
								theme: '#28FF28',
							});

							dp.seek(webdata.get('pay' + m3u8url));
							setInterval(function() {
									webdata.set('pay' + m3u8url, dp.video.currentTime);
								},
								1000);
						}
						$('#loading').hide();
						$('#player').show();
						
					} else if (data['code'] == '404') {
						if ('<?php echo $user['byjx']?>' != '') {
							var u = '<?php echo $user['byjx'].$url ?>';
							$("#player").html(
								'<iframe frameborder=0 marginheight=0 marginwidth=0 scrolling=no src="' + u +
								'" width="100%" height="100%" allowfullscreen="true"></iframe>'
							);
							$("#error").hide();
							$("#loading").hide();
							$("#player").show();
						} else {
							$('#loading').hide();
							$('#player').hide();
							$('#error').show();
							if (data['msg']) {
								$('#error').html('<h1>' + data['msg'] + '</h1>');
							}
						}
					}
				}, "json");
		}
		player();

		function playerstop() {
			var next = location.href.toLowerCase().split('next=');
			if (next.length > 1 && next[1].indexOf('http') == 0) {
				parent.location.href = next[1];
			} else if (next.length > 1) {
				alert(decodeURI(next[1]));
			}
		}

		function GetQueryString(name) {
			var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)");
			var r = window.location.search.substr(1).match(reg);
			if (r != null) return r[2];
			return null;
		}
	</script>
	<body style="overflow-y:hidden;">
		<div id="player" class="content" style="display:none;"></div>
		<div id="gg" class="gg" style="display:none;position:absolute;"></div>
		<div id="loading" align="center">
			<strong><br>
				<br>
				<br>
				<br>
				<br>
				<span class="tips">
					<p style="color:white;">
						正在加载中,请稍等....
						<font class="timemsg">0</font>s
					</p>
				</span></strong> <span class="timeout" style="display:none;color:#f90;">服务器响应超时，请刷新重试！</span>
		</div>
		<script type="text/javascript">
			function tipstime(count) {
				$('.timemsg').text(count);
				if (count == 15) {
					$('.tips').hide();
					$('.timeout').show();
				} else {
					count += 1;
					setTimeout(function() {
						tipstime(count);
					}, 1000);
				}
			}
			tipstime(0);

				//dp.notice('11', 2000, 0.8); 提示文本
				

		</script>

		<div id="error" class="content" style="display:none;padding-top:90px;color:white;" align="center"></div>

		<?php 
if($user['tj']!=''){
	$tongji='<div style="dis play:none">
<script type="text/javascript" src="'.$user['tj'].'"></script>';
		echo $tongji;
	}
?>
		</div>

	</body>
</html>
