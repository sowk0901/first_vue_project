<template>
<header>
      <div style="width: 10%;"><img src = "logo.png" style="width:90%"></div>
      <div id = "search">검색창</div>
      <input type="button" value="로그인 버튼">
   </header>
  <main>
    <div v-if="selectedBook.no" id = "book-card">
      <div>{{ selectedBook.no }}</div>
      <div>{{ selectedBook.week }}</div>
      <div>{{ selectedBook.tags }}</div>
      <button>읽기</button>
   </div>
   <div v-for="book of books" v-bind:key="book.no" class="book-button">
      <button v-on:click="selectedBook = book">
          <span>{{ book.no }}</span>
          <span>{{ book.week }}</span>
          <span>{{ book.tags }}</span>
      </button>
   </div>
  </main>
</template>

<script>
export default {
  name: 'App',

  data() {
    return{
      books: [
      {no: 1585 , week: '2023년 9월 둘째 주' , tags: ['친교/광고', '68기 어울팅', '66기 어울팅', '새가족 인터뷰', 'QT나눔']},
      {no: 1584 , week: '2023년 9월 첫째 주' , tags: ['친교/광고', 'QT나눔']},
      {no: 1583 , week: '2023년 8월 넷째 주' , tags: ['친교/광고', '하기봉사#2', '수련회#2', 'QT나눔']},
      {no: 1582 , week: '2023년 8월 셋째 주' , tags: ['친교/광고', '하기봉사', '수련회']},
      {no: 1581 , week: '2023년 8월 둘째 주' , tags: ['친교/광고', '간증']},
      {no: 1580 , week: '2023년 8월 첫째 주' , tags: ['친교/광고']},
      ],
      
      selectedBook: {},
      }
    },
  }
</script>

<style>
  header { display: flex; margin-bottom: 10px }
  header #search { flex: 1 1 0; background-color: #e6e9ed; border-radius: 5px; padding: 5px }
  main .book-button { display: flex; padding: 10px; margin-bottom: 10px; justify-content: center; overflow: hidden; text-overflow: hidden; white-space: nowrap }
  main .book-button span:nth-child(1) { color: #6d7695; font-weight: bold; min-width: 50px } /* nth-child(1)은 no구역 */
  main .book-button span:nth-child(2) { color: #777; min-width: 150px; font-weight: bold } /* nth-child(2)은 week구역 */
  button { background: e6e9ed; border: none; cursor: pointer; width: 80%; overflow:  hidden; }
  #book-card { position: fixed; bottom: 50px; left: 10%; width: 80%; background: yellow;}
</style>
