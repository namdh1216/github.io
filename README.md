테마는 좋아하는 게임에서 영감을 얻어 제작하였습니다.
https://www.youtube.com/watch?v=StyljKLvjGg&t=1274s <= 참고영상
기능 소개
마우스 휠을 돌리면 움직입니다.
각 프로젝트나 나의 스킬을 클릭하면 화면이 확대되며 타이핑 효과가 나옵니다.
타이핑 효과가 바로 설명들 입니다.
스페이스바를 누르면 희망 직무가 나옵니다.
한번더 누르면 꺼집니다.
닫기 눌러도 꺼집니다.
프로젝트는 진행하고 있는게 게임 기획 외에는 진행되는게 없습니다.
부가설명
나의 스킬은 게임의 주인공이 스킬을 얻는 장면에서 나오는 씬을 이용하였습니다.
타이핑 효과로 설명이 나오는 이유는 영감을 얻은 게임에서 연출 방법으로 타이핑 효과가 나오기 때문에 영감을 얻어 이용했습니다>(참고영상 참조)

기능들을 코드와 함께 설명하겠습니다.
3D 캐러셀 이동

설명: 마우스 휠을 돌리면 캐러셀이 좌우로 부드럽게 회전합니다.

코드 위치: script 태그 내 window.addEventListener('wheel', ...)

코드 설명: deltaY 값을 이용해 rotY를 갱신하고, .carousel 요소의 transform: translateZ(-1000px) rotateY(rotY) 스타일을 업데이트합니다.

프로젝트 클릭 확대 & 배경 전환

설명: 프로젝트를 클릭하면 섬네일이 확대되고, 각 프로젝트에 맞는 배경 비디오가 나오고 배경 이미지가 바뀝니다.

코드 위치: items.forEach(it => it.addEventListener('click', ...))

코드 설명: 클릭된 .carousel__item의 data-project 값을 확인해 #enlarge-img를 애니메이션으로 확대하고, #bg-video, #plan-video, #crowd-video, #web-video 또는 body.style.background 속성을 조정합니다.

타이핑 효과

설명: 확대된 화면에서 타이핑 효과가 출력됩니다.

코드 위치: function typeLoop(list, cls, idx) 및 imgEl.classList.add('glow-border') 이후 호출

코드 설명: setInterval로 글자를 한 글자씩 출력하고, 출력 완료되면 화면에 표시되다 서서히 사라진 다음 다음 문구가 출력됩니다. 타이핑 요소는 색이 다 다르게 나옵니다.

스페이스바 팝업 기능

설명: 스페이스바를 누르면 자기소개 팝업이 나타나며, 다시 누르거나 "닫기" 버튼을 누르면 팝업이 닫힙니다.

코드 위치: document.addEventListener('keydown', ...) 및 document.getElementById('intro-close').addEventListener

코드 설명: e.code === 'Space' 조건으로 body.intro-active 클래스를 토글하여 #intro-overlay의 opacity와 pointer-events를 변경하고, 팝업의 스케일 애니메이션을 적용합니다.

팝업 닫기 버튼

설명: 팝업 내부의 "닫기" 버튼을 클릭하면 팝업이 닫힙니다.

코드 위치: #intro-close 버튼 이벤트 리스너

코드 설명: 버튼 클릭 시 body.classList.remove('intro-active')로 팝업을 숨깁니다

배경 비디오 & 오디오 재생

설명: 페이지 로드 시 기본 배경 비디오가 자동 재생되고, 클릭된 프로젝트에 맞는 오디오가 루프 재생됩니다.

코드 위치: <video id="bg-video"> 요소 및 const audio = { ... } 초기화, audio[project].play() 호출

코드 설명: HTML5 <video>와 <audio> 요소를 미리 로드하고, JavaScript에서 play()와 pause()를 호출해 프로젝트 전환 시 오디오 트랙을 제어합니다.

https://github.com/namdh1216/github.io
