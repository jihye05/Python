import random   # 파이썬에서 제공하는 random 모듈

score = []  # 게임 성적 저장할 리스트
while True: # 사용자가 끝내기 전까지 게임 무한 반복
    print("UP & DOWN 게임에 오신걸 환영합니다~")
    print("1.게임시작 2.기록보기 3.종료하기")
    print(">>", end="")
    menu = int(input())     # 게임 시작 후 메뉴 선택
    ans = random.randrange(1, 101) # 1~100사이의 난수
    count = 1  # 게임 실행 횟수 저장할 변수
    start = 1  # 시작 숫자
    end = 100  # 끝 숫자


    while count < 11:   # 10번까지 게임 진행 가능
        if menu == 1:
            try:    # try~except문 사용해서 에러처리 하기
                num = int(input("%d번째 숫자 입력(%d ~ %d) : " % (count, start, end)))
                if num > ans:  # 입력한값이 정답(난수)보다 크면 down 출력
                    if num<end: # 피드백 1.입력한 범위 축소된 경우 다시 늘어나지 않게 하기
                        end = num  # 입력한 값을 1~end 형식이 되도록함.
                        print("down")
                        count += 1  # 입력 횟수 1증가
                elif num < ans:  # 입력한 값이 정답(난수)보다 작으면 up 출력
                    if num>start:   # 피드백 1.입력한 범위 축소된 경우 다시 늘어나지 않게 하기
                        start = num  # 입력한 값이 start~100 형식이 되도록 함.
                        print("up")
                        count += 1  # 입력 횟수 1증가
                else:
                    print("정답입니다!!")  # 정답 출력
                    print(count, "번째만에 맞추셨습니다.\n")  # 몇회만에 맞췄는지 출력
                    score.append(count)  # score리스트에 성공횟수 저장
                    max = score[0]  # 리스트의 제일 앞에 값을 max로 설정

                    for s in range(1, len(score)):  # max값보다 적은 횟수의 score가 나오면 최고기록경신 출력
                        if max > score[s]:
                            max = score[s]
                            print("최고기록경신~!!")  # 피드백 3. 최고기록일때 기록 추가
                            date = input("날짜를 입력해주세요")  # 최고기록 갱신시 날짜, 닉네임, 최고기록 저장
                            nickname = input("닉네임을 입력해주세요")
                            f = open('gamescore.txt', 'a')
                            f.write(str(max) + ' ' + date + nickname)  # 최고기록 날짜 닉네임 순으로 저장
                            f.write('\n')
                            f.close()
                    break

            except: # 피드백 2. 정답 1~100범위 안에서만 가능하게 하기
                print("1~100사이 숫자로 다시 입력해주세요")


        elif menu == 2: # 2.기록보기 눌렸을 경우
            score.sort()    # score 정렬
            for rank, value in enumerate(score, start=1):   # 등수 점수 순으로 나오도록 출력, 시작값은 0이아닌 1등으로 설정
                print(rank, value)
            break

        elif menu == 3:
            print("종료하겠습니다.")
            f = open('gamescore.txt', 'r')
            while True: # 반복문으로 파일 내용 읽고 종료하기
                line = f.readline()
                if not line: break
                print(line)
            exit()

        else:   # 피드백 4. 메뉴에 해당하지 않는 숫자 누른 경우
            print("1~3에서 메뉴 선택해주세요")
            break


# 피드백 5번 처음 답을 맞추는 경우에는 기록이 없어서 무조건 최고기록 멘트가 출력되어야 하는 것 더 실습해보고 추가하겠습니다.
