---
title: "일반 클라이언트 쪽 웹 기술"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | 일반 클라이언트 쪽 웹 기술"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e8e156552fd4aa733594c01845fb7ed1643b4aef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="common-client-side-web-technologies"></a>일반 클라이언트 쪽 웹 기술

> "웹 사이트 내부에서 제대로 표시를 종료 합니다."  
> _- Paul Cookson_

## <a name="summary"></a>요약

ASP.NET Core 응용 프로그램은 웹 응용 프로그램 및 일반적으로 HTML, CSS 및 JavaScript와 같은 클라이언트 쪽 웹 기술을에 의존 합니다. 레이아웃 및 스타일 (CSS) 및 (JavaScript)를 통해 해당 동작에서 페이지 (HTML)의 콘텐츠를 분리 하 여 복잡 한 웹 앱 Separation 원칙을 활용할 수 있습니다. 구조, 디자인 또는 응용 프로그램의 동작을 나중에 변경 내용 경우 수행할 수 더 쉽게 이러한 문제는 상호 연결 되어 있지 합니다.

HTML 및 CSS은 상대적으로 안정적인, JavaScript, 응용 프로그램 프레임 워크를 사용 하 여 유틸리티 개발자가 웹 기반 응용 프로그램을 빌드할 작업할가 보고 하는 동안 breakneck 속도로 진화 됩니다. 이 장에서 몇 가지 방법을 JavaScript 웹 개발자가 반응 하 고 각 클라이언트 쪽 라이브러리의 상위 수준 개요를 제공 하는 대로 응용 프로그램 개발의 일환으로 사용 하는 검토 합니다.

## <a name="html"></a>HTML

HTML (HyperText Markup Language)은 웹 페이지 및 웹 응용 프로그램을 만드는 데는 표준 표시 언어입니다. 해당 요소는 서식 있는 텍스트, 이미지, 입력을 구성 및 다른 구조로 나타내는 페이지의 구성 요소를 형성 합니다. 브라우저 페이지나 응용 프로그램을 인출 하는지 여부를 URL로 요청을 하면, 즉 먼저 반환 되는 HTML 문서입니다. 이 HTML 문서 참조 하거나 CSS 또는 JavaScript의 형태로 동작의 형태로 해당 모양 및 레이아웃에 대 한 추가 정보를 포함할 수 있습니다.

## <a name="css"></a>CSS

CSS (Cascading 스타일 시트) 모양과 레이아웃을 HTML 요소를 제어 하는 데 사용 됩니다. CSS 스타일 수 HTML 요소에 직접 적용, 동일한 페이지에 별도로 정의 된 또는 별도 파일에 정의 되어 있으며 페이지에서 참조. 스타일 연속 하는 지정 된 HTML 요소를 선택 하는 방법에 따라 변경 됩니다. 예를 들어, 스타일 문서 전체에 적용 될 수 있지만 특정 요소에 적용 되는 스타일에 의해 재정의 됩니다. 마찬가지로, 요소 관련 스타일이 차례로 (id)를 통해 해당 요소의 특정 인스턴스를 대상으로 하는 스타일을 재정의 해야 할 하는 요소에 적용 된 CSS 클래스에 적용 되는 스타일에 의해 재정의 됩니다. 그림 6-1

**그림 6-1입니다.** 순서 대로 CSS 특이성 규칙

![](./media/image6-1.png)

별도 스타일 시트 파일 자체에 스타일을 유지 하 고 응용 프로그램 내에서 일관 되 고 재사용 가능한 스타일을 구현 하 연계 선택 기반을 사용 하도록 가장 좋습니다. HTML 내에서 스타일 규칙 배치 피해 야 하 고 예외 규칙이 아니라 특정 개별 요소 (모든 종류의 요소나 특정 CSS 클래스에 적용 된 적이 있는 요소가 아님)에 스타일을 적용 해야 합니다.

### <a name="css-preprocessors"></a>CSS 프로세서

CSS 스타일 시트에는 조건부 논리, 변수 및 다른 프로그래밍 언어의 기능에 대 한 지원을 부족합니다. 따라서 큰 스타일 시트 자주 포함 반복을 많이 같은 색, 글꼴, 또는 기타 설정 HTML 요소 및 CSS 클래스의 여러 다른 변형에 적용 됩니다. CSS 프로세서를 수행 하 여 스타일 시트를 도와주는 [건조 원칙](http://deviq.com/don-t-repeat-yourself/) 변수 및 논리에 대 한 지원을 추가 하 여 합니다.

CSS 프로세서를 가장 많이 사용 되는 Sass 및 작은입니다. 둘 다 CSS를 확장 하 고 일반 CSS 파일을 올바른 Sass 또는 LESS 파일이 즉, 이전 버전과 호환 됩니다. Sass Ruby 기반 및 JavaScript 기반, LESS는 이며 일반적으로 둘 다 로컬 개발 프로세스의 일환으로 실행 합니다. 명령줄을 실행 하기 위한 Visual Studio에서 사용할 수 있는, 뿐만 아니라 기본 제공 지원 도구 명령을 둘 다 Gulp / Grunt 작업을 사용 하 여 합니다.

## <a name="javascript"></a>JavaScript

JavaScript는 ECMAScript 언어 사양에 표준화 된 프로그래밍 한 언어 동적, 해석 합니다. 웹의 프로그래밍 언어는 합니다. CSS와 같은 스크립트를 페이지 내 또는 별도 파일에 블록으로 JavaScript HTML 요소 내에서 특성으로 정의할 수 있습니다. CSS에서와 마찬가지로 것이 일반적으로 좋습니다 별도 파일에 JavaScript를 구성 하 응용 프로그램 뷰 또는 개별 웹 페이지에 HTML에서 최대한 많은 신경을 쓰지 않아도 유지.

웹 응용 프로그램에서 JavaScript를 작업할 때 수행 해야 일반적으로 몇 가지 작업이 있습니다.

-   HTML 요소를 선택 하 고 검색 및/또는 업데이트 해당 값

-   데이터에 대 한 웹 API를 쿼리합니다.

-   웹 API에 대 한 명령을 보내는 (및 그 결과 함께 콜백을에 응답)

-   유효성 검사를 수행합니다.

JavaScript 단독으로 이러한 작업 모두를 수행할 수 있지만 이러한 작업을 쉽게 수행할 수 있도록 다양 한 라이브러리 존재 합니다. 첫 번째 및 이러한 라이브러리 중 가장 성공적으로 실행 중 하나에 계속 해 서 웹 페이지에 이러한 작업을 단순화 하기 위한 많이 선택 되는 jQuery입니다. 단일 페이지 응용 프로그램 (SPAs), jQuery 각 및 반응 제공 하는 원하는 기능을 많이 제공 하지 않습니다.

### <a name="legacy-web-apps-with-jquery"></a>JQuery 사용 하 여 레거시 웹 앱

하지만 JavaScript 프레임 워크 표준에 의해 고 대, jQuery 여전히 HTML/CSS로 작업 하 고 웹 Api에 대 한 AJAX 호출을 수행 하는 응용 프로그램을 구성 하기 위한 매우 자주 사용 되는 라이브러리입니다. 그러나 jQuery 브라우저 문서 개체 모델 (DOM)의 수준에서 작동 하 고 기본적으로는 필수적인 경우 보다는 선언적 모델을 제공 합니다.

예를 들어 입력란의 값이 10을 초과 하는 경우 페이지에서 요소 수 있도록 표시 한다고 가정 합니다. JQuery,이 일반적으로 구현할 수 및 해당 값에 따라 대상 요소의 표시 유형을 설정 하 고 입력란의 값을 검사 하는 코드와 이벤트 처리기를 작성 하 여 합니다. 명령형 코드 기반 방법입니다. 대신 다른 프레임 워크 데이터 바인딩을 사용 하 여 하 고 입력란의 값에 따라 요소의 표시 여부를 선언적으로 바인딩할 수 있습니다. 이 코드를 작성이 필요 하지는 하지만 대신 포함 된 데이터 바인딩 특성을 가진 요소를 데코레이팅하만 필요 합니다. 클라이언트 쪽 동작 더 복잡 한 성장 함에 따라 데이터 바인딩을 자주 결과 적은 코드 및 조건부 복잡성을 사용 하 여 간단한 솔루션에 가깝습니다.

### <a name="jquery-vs-a-spa-framework"></a>jQuery vs SPA 프레임 워크

| **Factor** | **jQuery** | **각도**|
|--------------------------|------------|-------------|
| DOM을 추상화합니다. | **예** | **예** |
| AJAX 지원 | **예** | **예** |
| 선언적 데이터 바인딩 | **No** | **예** |
| MVC 스타일 라우팅 | **No** | **예** |
| 템플릿 | **No** | **예** |
| 딥 링크 라우팅 | **No** | **예** |

다른 라이브러리를 추가 하 여 대부분의 jQuery에 게 없는 경우 기본적으로 기능을 추가할 수 있습니다. 그러나 각 같은 SPA 프레임 워크와 시작부터 이러한 모든 기능은 이후 더 통합 된 방식으로 이러한 기능을 제공 합니다. 또한 jQuery는 jQuery를 사용 하 여 작업을 수행 하기 위해 jQuery 함수를 호출 할 경우를 의미 하는 매우 명령적 라이브러리. 많은 작업 및 SPA 프레임 워크를 제공 하는 기능 수행할 수 있습니다, 선언적 필요 없는 실제 코드를 작성 합니다.

데이터 바인딩은이의 좋은 예입니다. JQuery에서 일반적으로 단 한 줄의 코드 DOM 요소의 값을 가져오는 또는 요소 값을 설정 하려면. 그러나 하면이 코드를 작성 해야이 요소의 값을 변경 해야 하는 언제 든 지 그리고 페이지에 여러 함수에서 경우에 따라 발생 합니다. 또 다른 일반적인 예 요소 표시 유형입니다. JQuery, 여기서 코드 작성 컨트롤에 표시 된 특정 요소가 있는지 여부를 여러 다른 위치 있을 수 있습니다. 데이터 바인딩을 사용할 때 이러한 경우에는 모든 코드가 작성 해야 합니다. 값 또는 요소에 문제가의 표시 여부를 단순히 바인딩하는 것을 *viewmodel* 페이지, 및의 변경 viewmodel 자동으로 반영 되는지가 바인딩된 요소에 있습니다.

### <a name="angular-spas"></a>각도 SPAs

AngularJS 세계에서 가장 인기 있는 JavaScript 프레임 워크 중 하나에 신속 하 게 되었습니다. 처음부터 다시 프레임 워크를 팀 각도 2를 다시 (사용 하 여 [TypeScript](https://www.typescriptlang.org/)) AngularJS에서 단순히 각도를 브랜딩 하 고 있습니다. 현재 버전 4에서 각 여전히 단일 페이지 응용 프로그램을 빌드하기 위한 강력한 프레임 워크입니다.

각 응용 프로그램 구성 요소에서 빌드됩니다. 구성 요소는 특정 개체와 HTML 서식 파일을 결합 하 고 페이지의 일부를 제어 합니다. 각의 문서에서 간단한 구성 요소는 다음과 같습니다.

```js
import { Component } from '@angular/core';

@Component({
    selector: 'my-app',
    template: `<h1>Hello {{name}}</h1>`
})

export class AppComponent { name = 'Angular'; }
```

구성 요소를 사용 하 여 정의 된는 @Component 데코레이터 함수는 구성 요소에 대 한 메타 데이터를 사용 합니다. 선택기 속성이 구성이 요소 표시될지 페이지 요소에 id를 식별 합니다. 템플릿 속성은 마지막 줄에 정의 되는 구성 요소의 이름 속성에 해당 하는 자리 표시자를 포함 하는 간단한 HTML 템플릿입니다.

구성 요소 및 DOM 요소 대신 템플릿을 사용 하 여 각 앱은 상위 수준 추상화 하 고 ("바닐라 JS" 라고도 함) 하는 JavaScript만 사용 하 여 작성 된 응용 프로그램 보다 더 적은 전체 코드 또는 jQuery에서 작동할 수 있습니다. 또한 각 클라이언트 쪽 스크립트 파일을 구성 하는 방식에 몇 가지 순서를 적용 합니다. 각 앱을 규칙에 따라 응용 프로그램 폴더에 있는 모듈 및 구성 요소 스크립트 파일이 포함 된 공통 폴더 구조를 사용 합니다. 관련된 된 빌드, 배포 및 응용 프로그램을 상위 폴더에 일반적으로 테스트 스크립트 각도입니다.

또한 각은 명령줄 인터페이스 (CLI) 도구 훌륭한 사용 합니다. 실행 되 고 GitHub에서 리포지토리를 복제 하기만 하면 개발 시작 하기 각도 로컬로 (이미 git 및 npm 설치 가정) 이루어져 \`npm 설치\` 및 \`npm 시작\`합니다. 이 외 각 프로젝트를 만들, 파일을 추가 하 고 테스트, 번들, 및 배포 작업을 지원 하기 위해 수 있는 자체 CLI 도구를 제공 합니다. 에 게 친숙함 tooling이 CLI를 사용 하면 각도 뛰어난 CLI 지원 기능을 제공 하는 ASP.NET Core와 특히 호환 있습니다.

Microsoft는 참조 응용 프로그램을 개발 했습니다 [eShopOnContainers](http://aka.ms/MicroservicesArchitecture), 각도 SPA 구현을 포함 합니다. 이 앱 온라인 상점의 shopping basket, 로드 및 표시 항목의 카탈로그에서 및 처리 순서 만들기를 관리 하는 Angular 모듈을 포함 합니다. 보고 하 고 샘플 응용 프로그램에서 다운로드 [GitHub](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebSPA)합니다.

### <a name="react"></a>대응

전체 제공 하는 각, 달리 뷰를 모델-뷰-컨트롤러 패턴 구현 React 우려만 합니다. 빌드는 SPA 필요 추가 라이브러리를 활용 하는 프레임 워크 라이브러리에만 않습니다.

React의 가장 중요 한 기능 중 하나는 가상 dom 사용 가상 DOM React 성능 (가상 DOM을 최적화할 수를 업데이트할 필요는 실제 DOM의 부분) 및 테스트 용이성 (반응 하 고 해당 가상 DOM와의 상호 작용을 테스트 하려면 브라우저가을 필요 없음)를 포함 하 여, 여러 가지 이점을 제공 합니다.

또한 react html 작동 방식에 거의 하지 않습니다. 엄격한 코드와 구분 (사용 하 여 참조 아마도 HTML 특성에 표시 되는 JavaScript에) 태그 반응는 것이 아니라 해당 JavaScript 코드 내에서 직접 HTML JSX로 추가 합니다. JSX는 순수 JavaScript 아래쪽으로 컴파일할 수 있는 HTML 형식의 구문을입니다. 예:

```js
<ul>
{ authors.map(author =>
    <li key={author.id}>{author.name}</li>
)}
</ul>
```

JavaScript를 이미 알고 있는 경우 React 학습 쉽게 있어야 합니다. 없는 훨씬 거의 배워야 할 필요성이 또는 특수 구문을 연관으로 각 또는 다른 인기 있는 라이브러리입니다.

React 전체 프레임 워크 아니어서 웹 API 호출 및 종속성 관리, 라우팅 등의 작업을 처리 하는 다른 라이브러리 일반적으로 좋습니다. 좋은 점은, 단점은 이러한 결정을 모두 완료 되 면 함께 제대로 작동 모든 선택한 라이브러리가 확인을 해야 하지만 이들 각각에 대 한 최상의 라이브러리를 선택할 수 있습니다. 좋은 출발점을 하려는 경우 같은 React 함께 호환 라이브러리 집합이 prepackages 반응 Slingshot 시작 키트를 사용할 수 있습니다.

### <a name="choosing-a-spa-framework"></a>SPA 프레임 워크 선택

프로그램 SPA를 지원 하기 위해 가장 잘 작동 고려는 JavaScript 프레임 워크 때 염두에서에 둬야 다음 고려 사항:

-   팀은 프레임 워크 및 해당 종속성 (일부 경우에 포함 하 여 TypeScript)를 알고 있습니까?

-   어떻게 opinionated는 프레임 워크를 하 고 작업을 수행 하는 기본 방법을 동의?

-   (또는 도우미 라이브러리)에 모든 앱에 필요한 기능?

-   잘 문서화 된 입니까?

-   활동 상태는 해당 커뮤니티? 새 프로젝트를 빌드 것으로 구축 된?

-   활동 상태는 해당 핵심 팀? 문제 해결 되 고 새 버전 되 고 정기적으로 전송 되?

JavaScript 프레임 워크 지속적으로 breakneck 속도 개선 합니다. 나중에 의존 하는 것이 후회. 합니다는 프레임 워크를 선택할 때의 위험을 완화 위에 나열 된 고려 사항을 사용 합니다. 특히 감안할 인 경우는 상용 지원을 제공 및/또는 대기업에서 개발 되는 프레임 워크를 것이 좋습니다.

> ### <a name="references--client-web-technologies"></a>참조-클라이언트 웹 기술
> - **HTML 및 CSS**  
> <https://www.w3.org/standards/webdesign/htmlcss>
> - **Sass vs입니다. 덜**  
> <https://www.keycdn.com/blog/sass-vs-less/>
> - **더 적은 노력으로 ASP.NET Core 응용 프로그램, Sass, 및 놀라운 글꼴 스타일 지정**  
> <https://docs.microsoft.com/aspnet/core/client-side/less-sass-fa>
> - **ASP.NET Core에서 클라이언트 쪽 개발**  
> <https://docs.microsoft.com/aspnet/core/client-side/>
> - **jQuery**  
> <https://jquery.com/>
> - **jQuery vs AngularJS**  
> <https://www.airpair.com/angularjs/posts/jquery-angularjs-comparison-migration-walkthrough>
> - **각도**  
> <https://angular.io/>
> - 대응  
> <https://facebook.github.io/react/>
> - **Slingshot 대응**  
> <https://github.com/coryhouse/react-slingshot>
> - **React vs 각도 2 비교**  
> <https://www.codementor.io/codementorteam/react-vs-angular-2-comparison-beginners-guide-lvz5710ha>
> - **2017의 5 최상의 JavaScript 프레임 워크**  
> <https://hackernoon.com/5-best-javascript-frameworks-in-2017-7a63b3870282>

>[!div class="step-by-step"]
[이전] (공통-웹-응용 프로그램-architectures.md) [다음] (develop-asp-net-core-mvc-apps.md)
