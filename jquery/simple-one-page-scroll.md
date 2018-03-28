# Simple one page scroll

`jquery`를 이용하여 간단한 원페이지 스크롤 기능을 만들어 보았다.

```html
<nav id="nav">
  <ul>
    <li><a href="#section1" title="section1">section1</a></li>
    <li><a href="#section2" title="section2">section2</a></li>
    <li><a href="#section3" title="section3">section3</a></li>
    <li><a href="#section4" title="section4">section4</a></li>
  </ul>
</nav>
<div id="container">
  <section id="section1"><h1>section 1</h1></section>
  <section id="section2"><h1>section 2</h1></section>
  <section id="section3"><h1>section 3</h1></section>
  <section id="section4"><h1>section 4</h1></section>
</div>
```

```js
$(function() {
  
  function myScroll(target) {
    var posTop = $(target).offset().top;
    $('html, body').animate({
      scrollTop: posTop
    }, 500);
  }
  
  $('#nav a').on('click', function() {
    $('#nav a').removeClass('active');
    $(this).addClass('active');
    var target = $(this).attr('href');
    myScroll(target);
    return false;
  });
  
});
```

[[View Codepen]](https://codepen.io/lovingweb/full/EEoGGK/)