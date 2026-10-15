document.documentElement.classList.add('js');
var $=function(s){return document.querySelector(s)},$$=function(s){return document.querySelectorAll(s)};

// Mobile menu
var t=$('#toggle'),n=$('#nav');
t.addEventListener('click',function(){t.setAttribute('aria-expanded',n.classList.toggle('open'));});

// Open-now status
var dot=$('#dot');
if(dot){
var H=[[8,18],[6.5,20],[6.5,20],[6.5,20],[6.5,20],[6.5,20],[7,21]],d=new Date(),h=d.getHours()+d.getMinutes()/60,r=H[d.getDay()],o=h>=r[0]&&h<r[1];
dot.className='dot '+(o?'open':'closed');
$('#statusText').textContent=o?'Open now. Come on in!':'Closed right now. See our hours on the Best Coffee page.';
}

// Pickers (mood and brew): buttons with data-msg write into #out
$$('[data-msg]').forEach(function(b){
b.addEventListener('click',function(){
$$('[data-msg]').forEach(function(x){x.classList.remove('on')});
b.classList.add('on');
$('#out').innerHTML=b.dataset.msg;
});
});

// Filters (events and menu): buttons with data-filter show items with matching data-cat
var f=$$('#filters .pill');
f.forEach(function(b){
b.addEventListener('click',function(){
f.forEach(function(x){x.classList.remove('on')});
b.classList.add('on');
var k=b.dataset.filter;
$$('[data-cat]').forEach(function(e){e.classList.toggle('hide',!(k==='all'||e.dataset.cat===k));});
});
});
