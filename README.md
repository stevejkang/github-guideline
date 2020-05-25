<a href="https://github.com/stevejkang/github-guideline"><img src="https://raw.githubusercontent.com/stevejkang/emoji-for-readme/master/emoji/triangular-ruler.png" align="right" width="90" height="90" /></a>

# github-guideline

  Personal github guideline about commit convention, git flow, issue/pull-request templates, etc.

 [![Last Commit](https://img.shields.io/github/last-commit/stevejkang/github-guideline.svg)](https://github.com/stevejkang/github-guideline/commits)

## 목차
  1. [Commit Convention](#1-commit-convention)
  2. [Git Flow & Branch](#2-git-flow--branch)
  3. Pull Request
  4. Issue

## 1. Commit Convention

### 1.1. 커밋의 정의

#### 1.1.1. 작성자

  커밋은 작업자가 직접 작업한 내용에 대해 커밋을 합니다.

#### 1.1.2. 단위

  커밋은 작업 하나의 단위가 되어야 합니다. 행동 하나의 단위가 되어서는 안됩니다.  
  예를 들어, `Case A`는 가능하지만 `Case B`는 커밋의 단위로 권장하지 않습니다.

  - `Case A`
    - CLI로 Vue.js 프로젝트를 설치한 경우
    - 오타를 고친 경우
    - 여러 개의 Dependency를 설치하여 프로젝트 기반을 만든 경우
    - 하나 이상의 Dependency를 설치하고 프로젝트 어딘가에 정의, 적용한 경우
  - `Case B`
    - Dependency를 설치한 경우

#### 1.1.3. 조건

  커밋은 임시로 저장 해두기 위한 장치로 사용해서는 안됩니다. 즉, 모든 커밋은 개발 당시에 완결된 코드만이 올라가야 합니다.

### 1.2. 커밋 메세지

  > -m 옵션은 사용하지 않습니다.

#### 1.2.1. 언어

  누구나 봤을 때 이해할 수 있도록 영어로 작성하는 것을 권장합니다.

#### 1.2.2. 구성

  아래의 구성을 반드시 따라야 합니다.

  - 모든 줄은 문장으로 구성되며, 첫 문자는 대문자로, 첫 단어는 현재형 동사로, 마침표는 사용하지 않아야 합니다. 기타 기호 또는 특수문자(emoji 포함)는 필요한 경우를 제외하고는 사용을 권장하지 않습니다.
    - 예외사항
      - 메소드명 `getMessage()`
      - 파일명 `getMessage.js`
    - 예시
      - `Fix calculation in process.uptime()`

  - 세 줄 이상 작성해야 하고, 커밋의 두 번째 줄은 반드시 비워야 합니다. 세 번째 줄의 항목부터 상세 내용을 추가( `-` + 내용)할 수 있습니다.
    - 예외사항
      - 오타 수정 `Fix typo`
    - 예시  
      ```
      Prevent multiple connection errors

      Catch error caused by network error
      - Use try catch expression
      ```

  - 이슈가 해결된 내용은 커밋 최하단에 `Fix #7`와 같은 용법으로 사용할 수 있습니다.

  - 커밋의 제목 또는 본문에 가장 먼저 나타나는 현재형 동사는 다음을 사용합니다.
    - **Fix** [기능수정]
      - `Fix A`: A 수정
      - `Fix A in B`: B의 A 수정
      - `Fix A which B/Fix A that B`: B인 A 수정
      - `Fix A to B/Fix A to be B`: B를 위해 A 수정 | B하기 위해 A 수정
      - `Fix A so that B`: A 수정해서 B (B 상태 강조)
      - `Fix A[issue|error|crash] where B`: B하는 A 수정
      - `Fix A when B`: B에 발생하는 A 수정
    - **Add** [추가(코드/테스트/문서)]
      - `Add A`: A 추가
      - `Add A for B`: B를 위한 A 추가
      - `Add A to B`: B에 A 추가
    - **Remove** [삭제(코드/문서)]
      > 보통 (unnecessary|useless|unneeded|unused|duplicated) + A 형태  
      - `Remove A`: A 삭제
      - `Remove A from B`: B에서 A 삭제
    - **Use** [사용]
      - `Use A`: A 사용
      - `Use A for B`: B를 위한 A 사용
      - `Use A to B`: B에 A 사용 (to-부정사 B 허용)
      - `Use A in B`: B에 A 사용 | B 내부에서 A 사용
      - `Use A instead of B`: B 대신에 A 사용
    - **Apply** [적용]
      - `Apply A`: A 적용
      - `Apply A to B`: B에 A 적용
    - **Refactor** [리팩토링(행위/기능/메소드)]
      - `Refactor A`: A 리팩토링
    - **Simplify** [단순화(행위/기능/메소드)]
      - `Simplify A`: A 단순화
    - **Update** [문서/리소스 버전 업]
      - `Update A`: A 최신화
      - `Update A to B`: A를 B로 최신화
      - `Update A for B`: B를 위한 A 업데이트
    - **Improve**/**Enhance** [향상/개선(테스트/커버리지/성능)]
      - `Improve A`: A 향상
    - **Make** [동작 변경]
      - `Make A B`: A를 B하게 하다 (to-부정사 B 허용) | A를 B로 만들다
    - **Implement** [Add 보다 큰 구현]
      - `Implement A`: A 구현
      - `Implement A to B`: B에 A 구현
    - **Correct** [(문법/타입 등을) 맞도록 수정]
      - `Correct A`: A를 맞게 하다
    - **Ensure**/**Make sure** [검증]
      - `Ensure A`: A를 확실하게 하다
    - **Prevent** [접근제한]
      - `Prevent A`: A를 막다
      - `Prevent A from B`: A를 B하지 못하게 막다
    - **Avoid** [(조건 등을) 피하다]
      - `Avoid A`: A를 피하다.
      - `Avoid A if B/Avoid A when B`: B일 때 A에 걸리지 않도록 하다
    - **Move** [이동(코드/문서)]
      - `Move A to B/Move A into B`: A를 B로 이동하다
    - **Rename** [이름 수정(코드/문서/메소드)]
      - `Rename A to B`: A를 B로 이름을 바꾸다
    - **Allow** [허용]
      - `Allow A to B`: A가 B할 수 있도록 허용
    - **Verify** [검증]
      - `Verify A`: A를 검증
    - **Set** [설정(변수/값)]
      - `Set A to B`: A를 B로 설정
    - **Pass** [파라메터]
      - `Pass A to B`: A를 B로 넘기다
    - **Disable** [비활성화]
      - `Disable A`: A를 비활성화 하다

## 2. Git Flow & Branch

### 2.1. 개요

#### 2.1.1. 정의

  Git Flow는 버전 관리 시스템(Version Control System, VCS)의 한 종류인 git을 통해 효율적으로 프로젝트를 관리하고 배포하기 위한 전략이자 브랜칭 관리 전략(Branch Management Strategy) 입니다. 실제 프로덕트를 개발하고 지속적으로 배포하는 조직에서 권장되는 방법이지만, 실제로 개발 조직에 적용하는 방식은 각기 다를 수 있습니다.

  > 아래에서는 Best Practice를 담으려 노력하였으나, 조직과 프로젝트의 성격에 맞게 조정이 필요할 수 있습니다.

  이 섹션에서 말하는 Branch는 Git Flow의 브랜칭 관리 전략을 따르는 브랜치에 대한 설명입니다. 따라서 기본적인 `git branch` 명령어에 대한 설명을 포함하지 않습니다. 즉, 기본적으로 branch를 만들고, 이동하며, 삭제하는 등의 기초지식이 요구됩니다.

### 2.2. 방법
  
  > Vincent Driessen이 제한한 Git Flow는 다음 [PDF](https://nvie.com/files/Git-branching-model.pdf)로 한 눈에 확인할 수 있습니다.

#### 2.2.1. 브랜치 전략

  Git Flow에서는 용도/환경에 따라 브랜치를 구분합니다. 메인 브랜치는 master, develop 브랜치가 해당되며, 그 외에 보조 브랜치는 feature, hotfix, release 브랜치 등이 해당됩니다.

  - **master**  
  프로젝트의 뿌리가 되는 브랜치로, 해당 브랜치의 HEAD는 production 환경에 배포되었거나, 곧 배포될 예정임(production-ready)을 의미합니다. 실제 서비스에서는 실 서버와 sync가 맞아야 합니다.  
  master 브랜치에 반영 혹은 병합된다는 것은 새 버전이 배포됨을 의미합니다. 보통  실제 서버로 빌드 & 배포하는 스크립트가 작동합니다.

  - **develop**  
  다음 배포를 위해 개발되고 있는 코드가 위치하는 브랜치. 실제 서비스에서는 개발 서버 혹은 테스트 서버와 sync가 맞아야 합니다.  
  develop 브랜치가 안정화되고, 배포 기능이 완성되면, master로 병합됩니다.
  
    <table>
      <thead>
          <tr>
              <th colspan=3>브랜치 상세</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td rowspan=3>develop</td>
              <td>시작브랜치</td>
              <td>master</td>
          </tr>
          <tr>
              <td>병합브랜치(방향/순서)</td>
              <td>master</td>
          </tr>
          <tr>
              <td>네이밍 규칙</td>
              <td>develop</td>
          </tr>
      </tbody>
    </table>

  - **feature**  
  feature 브랜치는 개발하고자 하는 기능을 개발하는 주축이 되는 브랜치입니다. 만약 애자일 방법론을 채택한 조직이라면, 스프린트 기간 중 하나의 스토리 혹은 하나의 에픽이 이에 해당할 수 있습니다.  
  이 브랜치는 성공적으로 develop에 병합되거나 필요성이 없어진 경우 삭제하여 관리할 수 있습니다.
  
    > 네이밍 규칙에서 `feature-*`가 본래 권장되는 형식이나, SourceTree 등 GUI 환경에서 폴더구조로 표시된다는 이점 때문에 `feature/*`로 사용하기도 합니다.

    <table>
      <thead>
          <tr>
              <th colspan=3>브랜치 상세</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td rowspan=3>feature</td>
              <td>시작브랜치</td>
              <td>dev</td>
          </tr>
          <tr>
              <td>병합브랜치(방향/순서)</td>
              <td>develop / master</td>
          </tr>
          <tr>
              <td>네이밍 규칙</td>
              <td>feature-* 또는 feature/*</td>
          </tr>
      </tbody>
    </table>

  - **work**  
  개인별 작업을 위한 브랜치. 이는 Git Flow에 해당하는 내용은 아니지만, optional하게 사용할 수 있는 브랜치로, feature에서 분기되어 기능 개발에 사용되며, 작업자별 원활한 작업을 위해 만드는 것을 권장합니다.
  
    > 일부 조직에서는 fork의 형태로 repository를 분리하는 방법을 채택하기도 합니다.
  
    <table>
      <thead>
          <tr>
              <th colspan=3>브랜치 상세</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td rowspan=3>work</td>
              <td>시작브랜치</td>
              <td>feature</td>
          </tr>
          <tr>
              <td>병합브랜치(방향/순서)</td>
              <td>feature / develop / master</td>
          </tr>
          <tr>
              <td>네이밍 규칙</td>
              <td>ex) steve-* 또는 steve/*</td>
          </tr>
      </tbody>
    </table>

  > WIP release, hotfix

#### 2.2.2. 배포 전략

  > WIP master/develop, release, hotfix

#### 2.2.3. 병합/푸시 전략

  > WIP rebase, merge

## Reference

  - [좋은 git commit 메시지를 위한 영어 사전](https://blog.ull.im/engineering/2019/03/10/logs-on-git.html)

## License

  MIT

## Author

  stevejkang <iam@juneyoung.io>
