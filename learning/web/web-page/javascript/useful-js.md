# \*Useful JS

basic sellector

```html
document.getElementById('')
```

* document.getElementById('target').innerHTML = '새로운 내용';
  * `<div>`나 `<span>` 같은 요소 안의 내용을 바꿀 때



* document.getElementById('target').style.color = 'red';  \
  document.getElementById('target').style.backgroundColor = 'black';  \
  document.getElementById('target').style.fontSize = '20px';
  * css change



* document.getElementById('target').classList.add('active');  \
  document.getElementById('target').classList.remove('hidden');  \
  document.getElementById('target').classList.toggle('dark-mode');
  * class 조작



* document.getElementById('btn').addEventListener('click', function() {  \
  console.log('클릭 이벤트 발동');  \
  });
  * event  걸기



* document.getElementById('target').hidden = true; // HTML5 속성
  * 요소 숨기기

***

```javascript
getElementByClassName()

ex)
document.getElementsByClassName('navbar-toggler')[0].addEventListener('click', function(){
    document.getElementsByClassName('list-group')[0].classList.toggle('show');
});
```



```javascript
querySelector()
querySelectorAll()

ex)
document.getElementsByquerySelector('.navbar-toggler').addEventListener('click', function(){
    document.getElementsByquerySelector('.list-group').classList.toggle('show');
});
// #써서 id가져오기 가능

document.getElementsByquerySelectorAll('.navbar-toggler')[0].addEventListener('click', function(){
    document.getElementsByquerySelectorAll('.list-group')[0].classList.toggle('show');
});
```

***

```css
.black-bg {
  display : none;
}

.show-modal {
  display : block;
}
```



```css
.black-bg {
  visibility : hidden;
  opacity : 0;
  transition : all 1s;
}
.show-modal {
  visibility : visible;
  opacity : 1;
}
```

*   display : none을 주면 애니메이션이 잘 동작하지 않기 때문에

    그거랑 비슷한 역할을 할 수 있는 visibility : hidden 을 사용



















