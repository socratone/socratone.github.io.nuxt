<!-- 개발 도구 -->
<template>
  <div>
    <Header />
    <Body>
      <Page>
        <h1>개발 도구</h1>
        <h2>이미지</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="html"
            alt="html icon"
            title="unsplash.com"
            description="이미지 다운로드"
            url="https://unsplash.com"
          />
          <ToolsItem 
            img="html"
            alt="html icon"
            title="svgbackgrounds.com"
            description="벡터 배경 이미지 다운로드"
            url="https://svgbackgrounds.com"
          />
          <ToolsItem 
            img="html"
            alt="html icon"
            title="flaticon.com"
            description="아이콘 다운로드"
            url="https://flaticon.com"
          />
          <ToolsItem 
            img="html"
            alt="html icon"
            title="iconmonstr.com"
            description="아이콘 다운로드"
            url="https://iconmonstr.com"
          />
          <ToolsItem 
            img="html"
            alt="html icon"
            title="picsum.photos"
            description="랜덤 이미지 목업"
            url="https://picsum.photos"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="cssspritestool.com"
            description="CSS Sprites"
            url="https://cssspritestool.com"
          />
          <ToolsItem 
            img="html"
            alt="html icon"
            title="svgsprit.es"
            description="SVG Sprites"
            url="https://svgsprit.es"
          />
          <ToolsItem 
            img="html"
            alt="html icon"
            title="realfavicongenerator.net"
            description="favicon 생성"
            url="https://realfavicongenerator.net"
          />
        </ul>
        <h2>비디오</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="html"
            alt="html icon"
            title="pexels.com"
            description="동영상 다운로드"
            url="https://pexels.com"
          />
        </ul>
        <h2>CSS</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="css"
            alt="css icon"
            title="css-tricks.com"
            description="CSS 다양한 도형 예제"
            url="https://css-tricks.com/the-shapes-of-css/"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="colorzilla.com"
            description="gradient 예제"
            url="https://colorzilla.com/gradient-editor"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="getcssscan.com"
            description="box-shadow 예제"
            url="https://getcssscan.com/css-box-shadow-examples"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="color.adobe.com"
            description="색 조합"
            url="https://color.adobe.com/ko/create/color-wheel"
          />
        </ul>
        <h2>애니메이션</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="css"
            alt="css icon"
            title="animate.style"
            description="CSS 애니메이션 프리셋"
            url="https://animate.style"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="cubic-bezier.com"
            description="CSS 애니메이션 cubic-bezier"
            url="https://cubic-bezier.com"
          />
        </ul>
        <h2>VALIDATOR</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="html"
            alt="html icon"
            title="validator.w3.org"
            description="HTML Validator"
            url="https://validator.w3.org"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="jigsaw.w3.org"
            description="CSS Validator"
            url="https://jigsaw.w3.org/css-validator"
          />
        </ul>
        <h2>TREND</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="javascript"
            alt="javascript icon"
            title="2020.stateofjs.com"
            description="State of JS"
            url="https://2020.stateofjs.com/en-US/technologies/front-end-frameworks/"
          />
          <ToolsItem 
            img="css"
            alt="css icon"
            title="2020.stateofcss.com"
            description="State of CSS"
            url="https://2020.stateofcss.com/en-US/technologies/css-frameworks/"
          />
        </ul>
        <h2>ETC</h2>
        <ul class="tools-item-container">
          <ToolsItem 
            img="html"
            alt="html icon"
            title="dev.w3.org"
            description="특수 문자 코드"
            url="https://dev.w3.org/html5/html-author/charref"
          />
        </ul>
      </Page>
    </Body>
  </div>
</template>

<style scoped>
  .tools-item-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
</style>