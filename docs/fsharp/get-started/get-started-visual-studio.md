---
title: 'Visual Studio에서 F #으로 시작.'
description: 'F # Visual Studio와 함께 사용 하는 방법에 알아봅니다.'
ms.date: 02/13/2017
ms.openlocfilehash: d392e3a93d5b13206f654e35a266e9d9569942fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-f-in-visual-studio"></a>Visual Studio에서 F #으로 시작.

F # 및 Visual F # 도구는 Visual Studio IDE에서 지원 됩니다.  를 시작 하려면 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)아직 없는 경우, 합니다.  이 문서에서는 Visual Studio 2017 Community Edition을 사용 하지만 사용할 수 있습니다 F # 원하는 버전으로 합니다.

## <a name="installing-f"></a>F # 설치 #

처음으로 Visual Studio를 다운로드 하는 경우 Visual Studio 설치 프로그램을 먼저 설치 됩니다.  설치 관리자에서 모든 버전의 Visual Studio 2017을 설치 합니다. 이미 있는 경우 설치를 클릭 하 여 **수정**합니다.

다음 작업의 목록이 표시 됩니다. F #는 다음과 같은 작업 중 하나를 통해 설치할 수 있습니다.

|작업|작업|
|--------|------|
| .NET Core 플랫폼 간 개발 | 동작 안 함-F #은 기본적으로 설치 |
| ASP.NET 및 웹 개발 | 동작 안 함-F #은 기본적으로 설치 |
| Azure 개발 | 동작 안 함-F #은 기본적으로 설치 |
| .NET을 사용한 모바일 개발 | 동작 안 함-F #은 기본적으로 설치 |
| 데이터 과학 및 분석 응용 프로그램 | 동작 안 함-F #은 기본적으로 설치 |
| .NET 데스크톱 개발 | 선택 **F # 데스크톱 언어 지원** 오른쪽에서 |
| 데이터 저장소 및 처리 | 선택 **F # 데스크톱 언어 지원** 오른쪽에서 |

그런 다음 클릭 **수정** 오른쪽 아래에 있습니다.  그러면 선택한 모든 항목이 설치 됩니다.  클릭 하 여 F # 언어 지원과 함께 Visual Studio 2017을 열고 다음 **시작**합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Visual Studio를 열면:

1. 에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트**합니다.

2.  새로 만들기 대화 상자에서를 아래에서 프로젝트 **템플릿**, 나타납니다 **Visual F #** 합니다.  F # 서식 파일을 표시 하려면이 옵션을 선택 합니다.

3. 선택 **.NET Core 콘솔 앱** 또는 **콘솔 응용 프로그램**합니다.

3. 선택 된 **알겠습니다** F # 프로젝트를 만드는 단추!  이제 F # 프로젝트를 솔루션 탐색기에 나타납니다.

## <a name="writing-your-code"></a>코드 작성

이제 시작 하겠습니다 먼저 일부 코드를 작성 합니다.  다음 사항을 확인는 `Program.fs` 파일을 연 상태 및 다음 내용에 다음을 바꿉니다.

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

이전 코드 예제에서 함수 `square` 라는 입력을 가져와서는 정의 된 `x` 여 스스로 곱합니다.  F #에서 사용 하기 때문에 [형식 유추](../language-reference/type-inference.md), 유형의 `x` 지정할 필요가 없습니다.  F # 컴파일러 곱하기 올바른지 종류를 이해 하 고에 형식을 할당 합니다 `x` 정도에 따라 `square` 호출 됩니다.  위로 가져가면 `square`, 다음이 표시 됩니다.

```
val square: x:int -> int
```

이 함수의 형식 서명이 라고 합니다.  다음과 같이 읽을 수 있습니다: "사각형 이라는 정수를 사용 하는 함수는 x는 정수를 생성 하 고"입니다.  지정 하는 컴파일러는 `square` 는 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이 지금은- *모든* 형식, 하지만 대신는 제네릭 형식의 폐쇄형 집합입니다.  선택 하는 F # 컴파일러 `int` 이 지점 하지만 메이커가 형식 시그니처 호출 하는 경우 `square` 가 다른 입력 형식, 같은 `float`합니다.

다른 함수 `main`, 정의 된으로 데코레이팅되 어는 `EntryPoint` 해당 프로그램 실행 F # 컴파일러에 지시 하는 특성 시작 해야 합니다.  다른 동일한 규칙에 따라 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 전달할 수 있는 명령줄 인수 및 정수 코드가 반환 됩니다 (일반적으로 `0`).

이라고 하는이 함수에는 `square` 의 인수와 함께 함수가 `12`합니다.  F # 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 되는 함수, 즉는 `int` 하 고 생성 한 `int`).  에 대 한 호출 `printfn` 은 형식 문자열에 지정 하는 것에 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하 여 형식이 지정 된 인쇄 기능 한 다음 결과 새 줄을 출력 합니다.

## <a name="running-your-code"></a>코드 실행

코드를 실행 하 고 키를 눌러 결과 확인할 수 있습니다 **ctrl + f 5**합니다.  디버깅 하지 않고 프로그램 실행 되 고 결과 볼 수 있습니다.  선택할 수 있습니다는 **디버그** 최상위 메뉴는 Visual Studio에서 항목을 선택 **디버깅 하지 않고 시작**합니다.

이제 Visual Studio가 팝업를 콘솔 창에 출력할지 다음을 나타납니다.

```
12 squared is 144!
```

지금까지  첫 번째 F # 프로젝트를 Visual Studio에서 만든 하 고, F # 함수는 해당 함수 호출의 결과 인쇄를 작성 하 고, 몇 가지 결과 보려면 프로젝트를 실행 했습니다.

## <a name="using-f-interactive"></a>F # Interactive를 사용 하 여

Visual F # 도구 Visual Studio에서 가장 유용한 기능 중 하나에 F # Interactive 창입니다.  해당 코드를 호출 하 고 결과 대화형으로 확인할 수 있는 프로세스에 코드를 통해 보낼 수 있습니다.

사용을 시작 하려면 강조 표시는 `square` 코드에 정의 된 함수입니다.  다음으로 저장 된 **Alt** 키를 누릅니다 **Enter**합니다.  F # 대화형 창에서 코드를 실행 합니다.  F # 대화형 표시 되는 창에 다음과 같이 표시 되어야 합니다.

```
>

val square : x:int -> int

>
```

에 대 한 동일한 함수 시그니처 표시는 `square` 함수 위로 가져갈 때 앞에서 본 하는 함수입니다.  때문에 `square` 은 F # Interactive 프로세스에 정의 된, 이제 서로 다른 값으로 호출할 수 있습니다.

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

이 함수를 실행, 결과 새 이름 바인딩합니다 `it`, 유형 및 값을 표시 하 고 `it`합니다.  각 줄을 종료 해야 참고 `;;`합니다.  이 어떻게 F # Interactive 알고 함수 호출이 완료 되 면입니다.  또한 F # Interactive에서 새로운 함수를 정의할 수 있습니다.

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

위의 정의 새 함수로 `isOdd`,이 `int` 홀수 인지를 확인 하 고! 반환 서로 다른 입력을 확인 하려면이 함수를 호출할 수 있습니다.  함수 호출 내에서 함수를 호출할 수 있습니다.

```
> isOdd (square 15);;
val it : bool = true
```

사용할 수도 있습니다는 [정방향 파이프 연산자](../language-reference/symbol-and-operator-reference/index.md) 값 두 함수에 파이프라인 할:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

정방향 파이프 연산자 등은 이후 자습서에서 다룹니다.

이것은 F # 대화형으로 수행할 수 있는에 간략만 합니다. 자세한 내용을 보려면 체크 아웃 [F #을 사용한 대화형 프로그래밍](../tutorials/fsharp-interactive/index.md)합니다.

## <a name="next-steps"></a>다음 단계

아직 하지 않는 경우 체크 아웃의 [둘러보기의 F #](../tour.md)는 F # 언어의 핵심 기능 중 일부에 대해 설명 합니다.  F #의 기능 중 일부에 대 한 개요를 제공 하 고 Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 예제를 제공 합니다.  사용할 수는 몇 가지 외부 리소스는 또한에서 보여 줍니다는 [F # 가이드](../index.md)합니다.

## <a name="see-also"></a>참고자료
 [Visual F#](index.md)  
 [F# 둘러보기](../tour.md)  
 [F # 언어 참조](../language-reference/index.md)  
 [형식 유추](../language-reference/type-inference.md)  
 [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)  
