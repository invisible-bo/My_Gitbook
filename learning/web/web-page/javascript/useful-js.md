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





