# Github PR 가이드

## 아래의 사항들을 꼭 지켜주세요

1. `main` 브랜치는 절대 건들지 않아요
2. main 브랜치를 기준으로 `Daisy` 브랜치를 따고, 그 아래에 해당 주를 기준으로 `Daisy-week2` 브랜치를 따요
    
    ```bash
    main | git switch -c Daisy
    Daisy | git switch -c Daisy-week2
    ```
    
3. `Daisy-week2` 브랜치에서 해당 위클리 미션을 진행하고, 그 주 **일요일 오후 23:59** 까지 PR 을 올려요.
이 때, PR 제목은 **[본인이름] Week{number}** 로 통일해주세요
4. PR을 올리고 본인 코드에 대해 셀프 리뷰를 진행해요.
5. PR을 올린 후 멘토님을 리뷰어에 등록해주세요. 
    
    ![스크린샷 2023-03-29 오후 2.10.59.png](Github%20PR%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%20774f6cea70284047ab7f6f1cf29836c0/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-03-29_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_2.10.59.png)
    
6. PR에 원하는 라벨을 붙여요. 이는 코드 리뷰를 진행해 줄 멘토들과 동료 수강생들을 위한 거예요.
    
    ```jsx
    
    매운맛🔥 : 뒤는 없습니다. 그냥 필터 없이 말해주세요. 책임은 제가 집니다.
    
    순한맛🐑 : 마음이 많이 여립니다..
    
    미완성 : 죄송합니다..
    ```
    
     - PR을 올린 후 바로 머지해주세요. 이는 conflict를 방지하고, 코드 리뷰하기 편함 때문이에요.
    
7. 그 다음 `Daisy` 브랜치에서 `pull`한 후, 머지된 `Daisy`에서 다시 `Daisy-week3` 브랜치를 따주세요.
    
    ```bash
    Daisy-week2 | git switch Daisy
    Daisy | git pull origin Daisy
    Daisy | git switch -c Daisy-week3
    ```
    
8. 리뷰어의 2주차에 대한 리뷰는 `Daisy-week3` 에서 반영해주세요.
    1. 반영시 커밋 메시지는 다음과 같이 통일합니다.
        
        refactor **(mentor)**: var 를 let 으로 수정
        

## 참고 자료

[Git checkout 과 switch 관련 참고 자료](https://stackoverflow.com/questions/57265785/whats-the-difference-between-git-switch-and-git-checkout-branch)
