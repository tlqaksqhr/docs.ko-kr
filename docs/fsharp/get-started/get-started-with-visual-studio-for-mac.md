---
title: 'Mac 용 Visual Studio에서 F #을 사용 하 여 시작'
description: 'F # Visual Studio를 사용 하 여 mac 용 사용 방법 알아보기'
ms.date: 07/03/2018
ms.openlocfilehash: 200c3a8fee072797a54d15d8989937f4cadb33e2
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874655"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Mac 용 Visual Studio에서 F #을 사용 하 여 시작

F # 및 Visual F # 도구는 Visual studio에서 for Mac IDE 지원 됩니다. 했는지 [설치 된 Mac 용 Visual Studio](install-fsharp.md#install-f-with-visual-studio-for-mac)합니다.

## <a name="creating-a-console-application"></a>콘솔 응용 프로그램 만들기

Mac 용 Visual Studio에서 가장 기본적인 프로젝트 중 하나에 콘솔 응용 프로그램입니다.  방법은 다음과 같습니다.  Mac 용 Visual Studio가 열리면:

1. 에 **파일** 메뉴에서 **새 솔루션**합니다.

2.  새 프로젝트 대화 상자에서 콘솔 응용 프로그램에 대 한 2 개의 다른 템플릿이 있습니다.  다른 하나는.NET Framework를 대상으로 하는.NET-> 합니다.  .NET Core는 다른 템플릿에->.NET Core를 대상으로 하는 앱입니다.  이 문서의 목적을 위해 템플릿 작동 해야 합니다.

3. 콘솔 앱에서 C# F #에 필요한 경우 변경 합니다.  선택 된 **다음** 앞으로 이동 하려면 단추!  

4. 프로젝트에 이름을 지정 하 고 앱에 대해 원하는 옵션을 선택 합니다.  선택한 옵션을 기반으로 생성 되는 디렉터리 구조에 표시 되는 화면의 측면에 미리 보기 창, 표시 합니다.  

5. **만들기**를 클릭합니다.  솔루션 탐색기에서 F # 프로젝트는 이제 표시 됩니다.

## <a name="writing-your-code"></a>코드 작성

보겠습니다 먼저 일부 코드를 작성 하 여 시작 하세요.  했는지를 `Program.fs` 파일 열려 있는 경우 및 다음 해당 콘텐츠를 다음으로 바꿉니다.

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

이전 코드 샘플에서는 함수 `square` 명명 된 입력을 가져와서는 정의한 `x` 을 단독으로 곱합니다.  F # 사용 하므로 [형식 유추](../language-reference/type-inference.md), 형식의 `x` 지정할 필요가 없습니다.  F # 컴파일러 곱하기 유효 형식에 대 한 이해 및 형식을 할당 합니다 `x` 하는 방법에 따라 `square` 라고 합니다.  위로 가져가면 `square`, 다음과 같이 표시 됩니다.

```
val square: x:int -> int
```

이 함수 형식 시그니처 라고 합니다.  다음과 같이 읽을 수 있습니다: "정사각형은 명명 된 정수를 사용 하는 함수 x는 정수를 생성 하 고".  컴파일러 했습니다 보면 `square` 를 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이-지금은 *모든* 형식 이지만 대신 제네릭 형식의 폐쇄형 집합입니다.  선택 하는 F # 컴파일러 `int` 지금은 지점 하지만 조정 됩니다 형식 시그니처 호출 하는 경우 `square` 다른 입력 형식에 같은 `float`합니다.

다른 함수를 `main`, 정의 된으로 데코 레이트 된는 `EntryPoint` F # 컴파일러는 프로그램 실행에 지시 하는 특성 시작 해야 합니다.  다른 동일한 규칙을 따릅니다 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 명령줄 인수를 전달할 수 있습니다 및 정수 코드가 반환 됩니다 (일반적으로 `0`).

이 함수를 호출 하는 것은 `square` 의 인수를 사용 하 여 함수 `12`합니다.  F # 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 하는 함수,는 `int` 생성 하 고는 `int`).  에 대 한 호출 `printfn` 은 형식 문자열에 지정 된 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하는 서식이 지정 된 인쇄 기능 및 다음 결과 새 줄을 출력 합니다.

## <a name="running-your-code"></a>코드 실행

코드를 실행 하 고 클릭 하 여 결과 볼 수 있습니다 **실행할** 최상위 메뉴에서 차례로 **디버깅 하지 않고 시작**합니다.  이 디버깅 하지 않고 프로그램을 실행 및 결과 볼 수 있습니다.

이제 Mac 용 Visual Studio를 나타나게 하는 콘솔 창에 출력 한 다음을 표시 됩니다.

```
12 squared is 144!
```

지금까지  Mac 용 Visual Studio에서 첫 번째 F # 프로젝트를 만든 하 고, F # 함수는 해당 함수 호출의 결과 출력을 작성 하 고, 일부 결과 보려면 프로젝트를 실행 했습니다.

## <a name="using-f-interactive"></a>F # Interactive 사용

최상의 기능의 Visual F # Mac 용 Visual Studio에서 도구 중 하나는 F # 대화형 창입니다.  해당 코드를 호출 하 고 결과 대화형으로 볼 수 있는 프로세스에 코드를 보내야 할 수 있습니다.

사용을 시작 하려면 강조 표시 된 `square` 함수 코드에 정의 합니다.  다음으로, 클릭 **편집** 최상위 메뉴에서.  다음 선택 **선택 F # Interactive로 보내기**합니다.  이 F # 대화형 창의 코드를 실행 합니다.  선택 영역을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 있습니다 또는 **선택 F # Interactive로 보내기**합니다.  표시는 F # 대화형 창에서 다음을 사용 하 여 표시 됩니다.

```
>

val square : x:int -> int

>
```

이 대 한 동일한 함수 시그니처를 보여 줍니다는 `square` 함수 위로 가져갈 때 앞서 보았던는 함수입니다.  때문에 `square` 는 이제 F # 대화형 프로세스에서 정의 된 다른 값을 사용 하 여 호출할 수 있습니다.

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

이 함수를 실행, 새 이름으로 결과 바인딩합니다 `it`, 형식 및 값 표시 `it`합니다.  각 줄을 종료 해야 참고 `;;`합니다.  이것이 어떻게 F # Interactive 알고 함수 호출 완료 되 면입니다.  또한 F # Interactive에서 새 함수를 정의할 수 있습니다.

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

위의 새 함수를 정의 `isOdd`를 사용 하는 `int` 홀수 인지를 확인!  서로 다른 입력을 사용 하 여 반환 값을 확인 하려면이 함수를 호출할 수 있습니다.  함수 호출 내에서 함수를 호출할 수 있습니다.

```
> isOdd (square 15);;
val it : bool = true
```

사용할 수도 있습니다는 [파이프 정방향 연산자](../language-reference/symbol-and-operator-reference/index.md) 두 함수에 값을 파이프라인에:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

나중에 자습서 정방향 파이프 연산자 등을 설명 합니다.

이 F # Interactive를 사용 하 여 수행할 수 있는 작업에 대해 간략히만 합니다.  자세한 내용은 체크 아웃 [F #을 사용한 대화형 프로그래밍](../tutorials/fsharp-interactive/index.md)합니다.

## <a name="next-steps"></a>다음 단계

이미 않았다면 체크 아웃 합니다 [F # 둘러보기](../tour.md), F # 언어의 핵심 기능 중 일부를 포함 합니다.  F #의 기능 중 일부의 개요를 제공 하 고 Mac 용 Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.  도 유용한 외부 리소스 사용할 수 있습니다에 표시 된 [F # 가이드](../index.md)합니다.

## <a name="see-also"></a>참고자료
 [Visual F#](../index.md)  
 [F# 둘러보기](../tour.md)  
 [F # 언어 참조](../language-reference/index.md)  
 [형식 유추](../language-reference/type-inference.md)  
 [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)  
