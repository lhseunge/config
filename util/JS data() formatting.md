```jsx
// 한글을 사용하는 요일을 위해서는 추가적으로 배열을 만들어서 사용합니다.
let day = ['일', '월', '화', '수', '목', '금', '토'];

let today = new Date();

//1번 포맷
let dateFormat1 = today.getFullYear() + '년 ' + (today.getMonth()+1) + '월 '
    + today.getDate() + '일 ' + day[today.getDay()] + '요일 '
    + today.getHours() + '시 ' + today.getMinutes() + '분 '
    + today.getSeconds() + '초'

//2번 포맷
let dateFormat2 = today.getFullYear() +
    '-' + ( (today.getMonth()+1) < 9 ? "0" + (today.getMonth()+1) : (today.getMonth()+1) )+
    '-' + ( (today.getDate()) < 9 ? "0" + (today.getDate()) : (today.getDate()) );

document.getElementById("datetime").innerText =
            (today.getMonth()+1) + '월 ' + today.getDate() + '일 ' + day[today.getDay()] + '요일 ' + "\n" +
            (today.getHours() < 11 ? "오전 " : "오후 ") + (today.getHours() < 11 ? today.getHours() : today.getHours() - 12) + '시 ' + today.getMinutes() + '분 '
```
