# ITtimes
뉴욕타임즈를 변형해서 만든, IT기사들을 모아놓은 영자신문인 IT타임즈

(2022년 3학년 2학기 프로젝트 9월~12월)

*************************



* 웹사이트 틀 잡기 - HTML, CSS
* API 가져오기 - newscatcher에서 제공하는 API (https://newscatcherapi.com/)
* 부가적인 것들, 꾸미기 - javascript, CSS

_9월~10월_
- HTML, CSS를 이용하며 간단한 틀을 만듦
- JS 기본 문법을 학습
- JS로 간단한 게임을 구현해보면서 더 학습하기
- 뉴스 API 가져오기

_11월~12월_
- 웹사이트 틀 만듦
- 코드 리펙토링
- 페이지네이션 기능가추가


**어려웠던 페이지네이션 기능**

<img src="https://user-images.githubusercontent.com/68066598/221126877-dee7bfe2-fded-41e3-9d7c-c983010e649f.png" width="300" height="100">

```js
    //페이지네이션
    const pagination = () => {
    //li태그들을 담아둘 변수
    let paginationHTML = ``
    //총 페이지 수 total_page
    //내가 현재 몇 페이지를 보고 있는지 page
    //내가 몇 번째 그룹에 있는지 page group
    let pageGroup = Math.ceil(page / 5)
    //마지막 페이지가 뭔지 last
    let last = pageGroup * 5
    //첫 페이지가 뭔지 first
    let first = last - 4
    //first-last 페이지 프린트
    for (let i = first; i <= last; i++) {
        paginationHTML += `<li class="page-item ${page == i ? "active" : ""}"><a class="page-link" href="#" onclick="moveToPage(${i})">${i}</a></li>`
    }
    document.querySelector(".pagination").innerHTML = paginationHTML
}

    //페이지네이션 기능 함수
    const moveToPage = (pageNum) =>{
    //1.이동하고 싶은 페이지를 알기
    page = pageNum
    console.log(page)
    //2.이동하고 싶은 페이지를 가지고 api 다시 호출해주기
    getNews()
}
```


**뉴스기사 검색하는 기능**

<img src="https://user-images.githubusercontent.com/68066598/221130033-2447a864-b27c-43ce-ba72-9fc29d67a6d6.png" width="300" height="100">
