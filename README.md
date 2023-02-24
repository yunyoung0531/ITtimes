# ITtimes
## 뉴욕타임즈를 변형해서 만든, IT기사들을 모아놓은 영자신문인 IT타임즈

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

![ezgif com-video-to-gif](https://user-images.githubusercontent.com/68066598/221143181-4a48c68c-9ef2-4c9c-a288-136f2110539a.gif)

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

![ezgif com-video-to-gif (1)](https://user-images.githubusercontent.com/68066598/221143588-e27453a8-9be9-4ef2-8b71-3cf65cb8480f.gif)

<img src="https://user-images.githubusercontent.com/68066598/221130033-2447a864-b27c-43ce-ba72-9fc29d67a6d6.png" width="300" height="100">

```js
    const getNewsByKeyword = async() => {
    //console.log("click")
    //1. 검색 키워드 읽어오기
    //2. url에 검색 키워드 붙이기
    //3. 헤더준비
    //4. url부르기
    //5. 데이터 가져오기
    //6. 데이터 보여주기

    let keyword = document.getElementById("search-input").value
    console.log("keyword", keyword)
    url = new URL(`https://api.newscatcherapi.com/v2/search?q=${keyword}&page_size=10&topic=tech`) //newcatcherapi.com 에서 searchnews 헤드라인 가져오기
    getNews()
}
```


**모바일 버전에서도 확인 할 수 있는 반응형 웹 사이트**

<img src="https://user-images.githubusercontent.com/68066598/221130954-710d4d23-2c64-4852-bd41-c9f352abaf9a.png" width="400" height="200">






![ezgif com-video-to-gif (1)](https://user-images.githubusercontent.com/68066598/221143588-e27453a8-9be9-4ef2-8b71-3cf65cb8480f.gif)


![ezgif com-video-to-gif (2)](https://user-images.githubusercontent.com/68066598/221143940-8b276517-6a91-4bf8-9ebd-8ab369579c8f.gif)
