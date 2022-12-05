# 브랜치 rebase의 이해와 실습
## 병합 rebase
- 분기된 브랜치의 부모 브랜치를 수정해 fast-forward 모양으로 수정됨
- `git rebase main`: HEAD 브랜치의 모든 커밋들을 main브랜치 이후로 추가
- `git merge (HEAD branch)`: main으로 이동해서 HEAD 브랜치로 병합 필요

## merge와 rebase 비교
- merge: 변경 내용의 이력이 모두 그대로 남아 있기 떄문에 이력이 복잡
- rebase: 히스토리가 선형으로 단순해 좀 더 깨끗함, 원래의 커밋 이력이 변경됨(정확한 이력 기록에는 사용 불가)

## `$git rebase <newparent> <branch>`
- 브랜치에서 부모브랜치의 최근 커밋 이후에 브랜치를 배치해 선형 병합

## 커밋이력 수정
- 최근 커밋 메세지를 설정된 편집기로 수정하는 방법 (code.editor)
- 최근 커밋 메세지를 직접 입력해 수정 (commit -am)
- 새로운 커밋ID로 수정
  
## rebase의 --interactive 사용
- 작업 공간이 깨끗해진 이후 이전 여러 개의 커밋을 수정(커밋을 다시 작성한 경우 새 ID 부여)
- 커밋 시퀀스를 새로운 기본 커밋에 결합: `$git rebase -i HEAD~3`(수정할 커밋의 직전 커밋)
### 주요 대화형 명령어
- p(ick): 해당 커밋을 수정하지 않고 그냥 사용
- r(eword): 개별 커밋 메세지를 다시 작성
- s(quash): 계속된 이후 커밋을 이전 커밋에 결합(p~s 순서로)
- d(rop): 커밋 자체를 삭제

