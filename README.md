# iframe
跨域通信 | 父子页面传值

父页面 ----> 子页面

父页面：
 var s = {"data":"parentData"}
 $("#iframe_fu")[0].addEventListener('load',function(){
    $("#iframe_fu")[0].contentWindow.postMessage(s,"*");
},false)

子页面：
window.addEventListener("message", function(e) {
		console.log(e.data)
},false)

子页面 ----> 父页面

父页面：
 window.addEventListener('message',function(e){
    console.log(e.data)
 }
 
 子页面：
 function postMessage(){
		var post = {
			"type":2
		}
		window.parent.postMessage(post,'*');
}
