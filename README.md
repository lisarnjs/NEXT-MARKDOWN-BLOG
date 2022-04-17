## NEXT-MARKDOWN-BLOG
**study with YouTube"Traversy Media"**

### Framework & Library
- next.js
- marked
- gray-matter

---

## Next.js STUDY

### Pre-rendering
**Static Generation**  
```
HTML is generatied at build time   
and will be reused on each request
```
- 데이터가 없는 경우의 Static Generation
  - 서버로부터 fetch해 올 어떠한 데이터도 없기 때문에 build time에 HTML 형태로 사전 렌더링 해둠
- 데이터가 있는 경우의 Static Generation
  - 페이지 컨텐츠가 외부 데이터에 의존할 경우
    - `getStaticProps`를 사용한다
  - 페이지 경로가 외부 데이터에 의존할 경우
    - `getStaticPaths`를 사용하는데, 보통 `getStaticProps`와 함께 사용함

`getStaticProps`
```
- Fetch data at build time using with props
```
`getStaticPaths`
```
- 사전 렌더링 하고 싶은 path를 build time에 특정할 수 있게 해줌
- {fallback: false}는 다른 라우트는 404를 띄워야 된다는 뜻
```
---  
**SSR(Server Side Rendering)**
```
HTML is generated on each request
```
- Static Generation에 비해서는 더 느리겠지만 사전에 렌더링된 페이지들은 항상 최신 상태를 유지한다.
- 외부 API로부터 fetch해 오는 페이지가 업데이트되는 데이터를 항상 사전 렌더링해야 할 경우, 이 데이터를 받아와서 Page로 넘기는 `getServerSideProps`를 사용해야함
  

`getServerSideProps`
```
- 매 요청시마다 getServerSideProps 함수가 호출됨
- props를 통해 페이지에 데이터를 전송한다.
```
  
*getStaticProps vs getServerSideProps*
- getStaticProps : pre-rendering at build time
- getServerSideProps : pre-rendering on each request