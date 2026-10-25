# appahanja-pictures

아빠한자 앱의 플래시카드 그림 묶음 (2급 이상, 급수별 zip).
앱이 jsDelivr 로 내려받는다: `https://cdn.jsdelivr.net/gh/karrel84/appahanja-pictures@v1/packs/<급수id>.zip`

- 파일 이름: `<한자 코드포인트 16진수>.webp` (512px)
- 3급까지 그림은 앱 안에 들어 있어 여기 없다.
- 그림은 로컬 이미지 모델(Z-Image Turbo)로 생성했다.

## manifest.json (그림 고침)

앱은 켤 때 `manifest.json`(raw.githubusercontent, main)을 읽어 급수별 묶음 버전을 본다.
가진 버전보다 높으면 `url` 의 zip 을 받아 덮어쓴다. 앱에 든 급수(8급~3급)는 버전 1로 친다.

새 그림을 올릴 때:
1. `tools/images/make_packs.py <버전> <급수>...` 로 `packs/<급수>-v<버전>.zip` 만들기
2. 커밋하고 새 태그(`p<버전>` 등)를 push — jsDelivr 는 태그 주소를 바로 낸다
3. manifest.json 의 그 급수 `v`·`url`·`bytes` 를 고쳐 main 에 push
