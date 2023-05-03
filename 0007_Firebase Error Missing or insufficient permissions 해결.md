# Firebase Error - 'Missing or insufficient permissions' 해결방법

파이어베이스에서 데이터를 받아오는데, 시뮬레이터를 통해 아래와 같은 오류가 생긴다면
혹은, 잘 되다가 갑자기 Firestore Database, Storage, Realtime Database가 되지 않는다면
```
Error writing document
com.google.firebase.firestore.FirebaseFirestoreException: PERMISSION_DENIED: Missing or insufficient permissions.
Caused by: io.grpc.StatusException: PERMISSION_DENIED: Missing or insufficient permissions.
                                                                                                    	
```

# 오류가 있는 해당 제품의 규칙 수정하기!!!
- 잠금모드, 테스트모드에 따라서 다르지만 테스트모드를 시작했을 때 보안 규칙을 제대로 설정하지 않는다면, 아예 파이어베이스 기반으로 하던 프로젝트가 작동되지 않을수도 있고, 처참한 상황 발생한다....
- 반드시, 파이어베이스 보안규칙 공식문서를 보며 다시 작성하는 것이 미래를 위해 옳다...

* Storage 보안규칙 쉽게 설명되어 있는 곳 : [Storage](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=lys1900&logNo=221013967856)
 
