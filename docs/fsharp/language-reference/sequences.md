---
title: 시퀀스(F#)
description: '대규모 데이터의 컬렉션을 정렬 되어 있지만 모든 요소를 사용 하려면 반드시 원하지 때 F # 시퀀스를 사용 하는 방법을 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: ebebec3a69fd0f4fb8e3ad8d554541fa1cc8945e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="sequences"></a>시퀀스

> [!NOTE]
이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

A *시퀀스* 논리는 일련의 요소는 특정 형식의 모든 합니다. 시퀀스는는 대형 데이터의 컬렉션을 정렬 되어 있지만 주로 모든 요소를 사용 하는 경우에 특히 유용 합니다. 시퀀스에 있는 요소를 모두 사용 되는 상황에서 목록 보다 더 나은 성능을 제공할 수 있도록 요소로만 계산 되는 개별 시퀀스 필요 합니다. 시퀀스도 표시 됩니다는 `seq<'T>` 별칭 형식에 대 한 `System.Collections.Generic.IEnumerable`합니다. 따라서 구현 하는.NET Framework 형식 `System.IEnumerable` 시퀀스도 사용할 수 있습니다. [Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 시퀀스가 관련 된 조작을 대 한 지원을 제공 합니다.

## <a name="sequence-expressions"></a>시퀀스 식
A *식 시퀀스* 시퀀스에 계산 되는 식입니다. 시퀀스 식에는 여러 가지 형식 걸릴 수 있습니다. 가장 간단한 형태는 범위를 지정합니다. 예를 들어 `seq { 1 .. 5 }` 1과 5 끝점을 포함 하 여 다섯 개의 요소를 포함 하는 시퀀스를 만듭니다. 있습니다 하거나 지정할 수는 증가 (감소) 두 double 기간 사이입니다. 예를 들어 다음 코드는 10을 곱한 값의 시퀀스를 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

시퀀스 식은 F # 식을 시퀀스의 값을 생성 하는 구성 됩니다. 사용할 수는 `yield` 키워드 시퀀스에 포함 되는 값을 생성 합니다.

다음은 예제입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

사용할 수 있습니다는 `->` 연산자 대신 `yield`, 생략할 수는 쿼리에서 `do` 키워드에 다음 예제와 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

다음 코드에서 눈금을 나타내는 배열 인덱스 함께 좌표 쌍 목록을 생성 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

`if` 시퀀스에 사용 된 식에는 필터입니다. 예를 들어, 소수로 함수 했다고 가정의 시퀀스를 생성 하려면 `isprime` 형식의 `int -> bool`, 시퀀스를 다음과 같이 작성 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

사용 하는 경우 `yield` 또는 `->` 반복에서 각 반복 하는 예상 되는 시퀀스의 단일 요소를 생성 합니다. 요소 시퀀스를 생성 하는 각 반복을 사용 하 여 `yield!`합니다. 이 경우 각 반복에 대해 생성 된 요소는 최종 시퀀스를 생성 하기 위해 연결 됩니다.

여러 개의 식을 시퀀스 식에서 함께 결합할 수 있습니다. 각 식에서 생성 된 요소를 서로 연결 됩니다. 예를 들어이 항목의 "예" 섹션을 참조 하십시오.

## <a name="examples"></a>예제
첫 번째 예제에서는 반복, 필터 및 yield 배열을 생성을 포함 하는 시퀀스 식을 사용 합니다. 이 코드는 1에서 콘솔에는 100 사이의 소수 숫자 시퀀스를 인쇄합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

다음 코드에서는 `yield` 각각의 두 가지 요소 및 제품 구성 된 3 개 요소의 튜플로 구성 된 곱하기 테이블을 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

다음 예제에서는 `yield!` 개별 시퀀스를 단일 마지막 시퀀스에 결합 하 합니다. 이 경우 이진 트리의 각 하위 트리의 시퀀스는 마지막 시퀀스를 생성 하는 재귀 함수에 연결 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]
    
## <a name="using-sequences"></a>시퀀스 사용
시퀀스를 지 원하는 다양 한 동일한 기능을 지원 [나열](lists.md)합니다. 시퀀스는 그룹화 키 생성 함수를 사용 하 여 계산 등 작업을 지원 합니다. 시퀀스는 또한 하위 시퀀스를 추출 하기 위한 더 다양 한 기능을 지원 합니다.

목록, 배열, 집합, 지도 등 대부분의 데이터 형식이 열거 가능한 컬렉션을 되기 때문에 암시적으로 시퀀스입니다. 상황에 따라 인수는 일반 F # 데이터 형식를 사용 하 여 또한 구현 하는 모든.NET Framework 데이터 형식에는 시퀀스를 사용 하는 함수 `System.Collections.Generic.IEnumerable<'T>`합니다. 이 목록에만 사용할 수 있습니다를 인수로 목록을 사용 하는 함수에는 대조 됩니다. 형식 `seq<'T>` 형식 약어에 대 한 `IEnumerable<'T>`합니다. 즉, 제네릭 구현 하는 형식 `System.Collections.Generic.IEnumerable<'T>`, 배열, 목록, 포함 된 설정 및 F #, 및도 대부분.NET Framework 컬렉션 형식을, 지도와 호환 되는 `seq` 입력 하 고 시퀀스 필요한 곳 마다 사용할 수 있습니다.


## <a name="module-functions"></a>모듈 함수
[Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 에 [Microsoft.FSharp.Collections 네임 스페이스](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) 시퀀스를 사용 하기 위한 함수를 포함 합니다. 이러한 함수 작업할 목록, 배열, 맵 및 집합도은 열거할 모든 해당 형식 이어서 시퀀스로 취급 될 수 있습니다.


## <a name="creating-sequences"></a>시퀀스 만들기
이전에 설명한 대로 시퀀스 식을 사용 하 여 또는 특정 기능을 사용 하 여 시퀀스를 만들 수 있습니다.

사용 하 여 빈 시퀀스를 만들 수 있습니다 [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), 하나만 지정 된 요소 시퀀스를 사용 하 여 만들 수 있습니다 또는 [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

사용할 수 있습니다 [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) 요소 제공 하는 함수를 사용 하 여 생성 됩니다는 순서를 만들려면 합니다. 또한 시퀀스에 대 한 크기를 제공합니다. 이 함수는 마찬가지로 [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)한다는 점을 제외 하는 요소 시퀀스를 반복 될 때까지 만들어지지 않습니다. 다음 코드에서는 `Seq.init`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

출력은 다음과 같습니다.

```
0 10 20 30 40
```

사용 하 여 [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) 및 [Seq.ofList&#60;' T&#62; 함수](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), 배열 및 목록에서 순서를 만들 수 있습니다. 그러나 변환할 수도 있습니다 배열과 목록을 시퀀스에는 캐스트 연산자를 사용 하 여 합니다. 두 가지 방법은 모두 다음 코드에 표시 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

사용 하 여 [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)에 정의 된 등의 약한 형식의 컬렉션에서 시퀀스를 만들 수 있습니다 `System.Collections`합니다. 이러한 약하게 형식화 된 컬렉션에서 요소 형식을 사용할 `System.Object` 하 고 제네릭이 아닌를 사용 하 여 열거 `System.Collections.Generic.IEnumerable&#96;1` 유형입니다. 다음 코드에서는 `Seq.cast` 변환 하는 `System.Collections.ArrayList` 시퀀스로 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

사용 하 여 무한 시퀀스를 정의할 수 있습니다는 [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) 함수입니다. 이러한 시퀀스에 대 한 요소의 인덱스에서 각 요소를 생성 하는 함수를 제공 합니다. 지연 계산; 인해 무한 시퀀스 생성할 수 있습니다. 요소를 지정 하는 함수를 호출 하 여 필요에 따라 만들어집니다. 다음 코드 예제에서는 부동 소수점 숫자를이 사례에서 교대로 반복 되는 일련의 연속 된 정수 제곱 평균은의 시퀀스를 생성 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) 계산 함수는 상태를 사용 하는 시퀀스의 각 후속 요소를 만드는 로부터 시퀀스를 생성 합니다. 상태는 각 요소를 계산 하는 데 사용 되 고 각 요소는 계산 된 변경할 수 있는 값 뿐입니다. 두 번째 인수를 `Seq.unfold` 는 시퀀스를 시작 하는 데 사용 되는 초기 값입니다. `Seq.unfold` 시퀀스를 반환 하 여 종료를 사용할 수 있는 상태에 대 한 옵션 종류를 사용 하 여 `None` 값입니다. 다음 코드는 시퀀스는 두 가지 예를 보여 줍니다. `seq1` 및 `fib`를 통해 생성 된는 `unfold` 작업 합니다. 첫 번째 `seq1`, 100 까지의 숫자로 이루어진 단순한 시퀀스 됩니다. 두 번째 `fib`, 사용 하 여 `unfold` 피보나치를 계산 합니다. 각 요소는 피보나치에서 이전 두 피보나치 숫자의 합 이기 때문에 상태 값은 시퀀스에서 이전 두 숫자의 구성 된 튜플을 합니다. 초기 값은 `(1,1)`, 시퀀스에서 처음 두 번호입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

출력은 다음과 같습니다.

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

다음 코드는 다양 한 여기에서 설명 생성 하 고 무한 시퀀스의 값을 계산 하는 시퀀스 모듈 함수를 사용 하는 예제입니다. 코드를 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]
    
## <a name="searching-and-finding-elements"></a>요소 검색 및 찾기
시퀀스 목록을 사용 하 여 사용할 수 있는 기능을 지 원하는 지원: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), 및 [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)합니다. 시퀀스에 사용할 수 있는 이러한 함수 버전에 대 한 검색 되는 요소까지만 시퀀스를 평가 합니다. 예제를 보려면 [나열](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)합니다.


## <a name="obtaining-subsequences"></a>시퀀스 가져오기
[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) 및 [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) 해당 함수는 필터링과 선택 시퀀스 요소를 계산할 때까지 발생 하지 않는 점을 제외 하 고 목록에 사용할 수 있는 같은 됩니다.

[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) 다른 시퀀스에서 시퀀스를 만들지만 시퀀스 요소의 지정 된 수를 제한 합니다. [Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) 요소 시퀀스의 시작 부분부터 지정한 수만 포함 하는 새 시퀀스를 만듭니다. 지정한 것 보다 더 적은 요소가 시퀀스에 있는 경우 `Seq.take` throw 한 `System.InvalidOperationException`합니다. 차이 `Seq.take` 및 `Seq.truncate` 은 `Seq.truncate` 요소의 수는 지정한 숫자 보다 적은 경우 오류를 생성 하지 않습니다.

다음 코드의 동작을 보여 줍니다과 차이점이 `Seq.truncate` 및 `Seq.take`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

출력 오류가 발생 하기 전에 다음과 같습니다.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

사용 하 여 [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), 조건자 함수 (부울 함수)를 지정 하 고 조건자는 원래 시퀀스의 해당 요소의 다른 시퀀스에서 시퀀스를 만들 수 있습니다 `true`, 하지만 중지 조건자 반환 하는 첫 번째 요소 앞 `false`합니다. [Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) 지정 된 수의 다른 시퀀스의 첫 번째 요소를 건너뛰고 나머지 요소를 반환 하는 시퀀스를 반환 합니다. [Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) 시퀀스 조건자 반환 다른 시퀀스의 첫 번째 요소를 반환 `true`, 다음 조건자 반환하는첫번째요소부터시작하고나머지요소를반환하고`false`.

다음 코드 예제에서는의 동작을 보여 줍니다과 차이점이 `Seq.takeWhile`, `Seq.skip`, 및 `Seq.skipWhile`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

출력은 다음과 같습니다.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>시퀀스 변환
[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) 튜플로 입력된 시퀀스의 연속 요소 그룹화 되는 새 시퀀스를 만듭니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) 비슷합니다 `Seq.pairwise`제외 튜플 시퀀스를 생성 하는 대신 인접 요소의 복사본을 포함 하는 배열의 시퀀스를 생성 하 고, (한 *창*) 시퀀스에서 합니다. 각 배열에 원하는 인접 한 요소 수를 지정 합니다.

다음 코드 예제에서는 `Seq.windowed`의 사용법을 보여줍니다. 이 경우에 창에 있는 요소의 수는 3입니다. 이 예제에서는 사용 `printSeq`를 이전 코드 예제에 정의 된 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

출력은 다음과 같습니다.

초기 시퀀스:

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>여러 개의 시퀀스를 사용 하는 작업
[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) 및 [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) 시퀀스 두 개 또는 세 개의 및 튜플 시퀀스를 생성 합니다. 이러한 함수는 해당 함수에 사용할 수 있는 유사 [나열](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)합니다. 시퀀스를 두 개 이상의 한 개의 시퀀스를 구분 하는 해당 기능은 없습니다. 시퀀스에 대 한이 기능을 해야 할 경우 목록에 시퀀스를 변환 하 고 사용 하 여 [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)합니다.


## <a name="sorting-comparing-and-grouping"></a>정렬, 비교 및 그룹화
목록에 대 한 지원 되는 정렬 함수 시퀀스와도 작동 합니다. 여기에 [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) 및 [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)합니다. 이러한 함수는 전체 시퀀스를 반복 합니다.

사용 하 여 두 시퀀스를 비교는 [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) 함수입니다. 연속 요소를 비교 하 고 같지 않은 첫 번째 쌍 발생 하면 중지 합니다. 추가 요소는 비교에 기여 하지 않습니다.

다음 코드는 `Seq.compareWith`의 사용법을 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

이전 코드에서 첫 번째 요소에만 계산 및 조사를 하 고 결과-1입니다.

[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) 라고 하는 값을 생성 하는 함수는 *키* 각 요소에 대 한 합니다. 각 요소에 대해이 함수를 호출 하 여 각 요소에 대 한 키가 생성 됩니다. `Seq.countBy` 키 값 및 키의 각 값을 생성 하는 요소의 수를 포함 하는 시퀀스를 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

출력은 다음과 같습니다.

```
(1, 34) (2, 33) (0, 33)
```

이전 출력 2, 키를 생성 하는 33 값과 0 키를 생성 하는 33 값 1, 키를 생성 하는 원래 시퀀스의 34 요소 했음을 보여 줍니다.

호출 하 여 시퀀스의 요소를 그룹화 할 수 있습니다 [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)합니다. `Seq.groupBy` 시퀀스 및 요소에서 키를 생성 하는 함수를 사용 합니다. 함수는 시퀀스의 각 요소에 대해 실행 됩니다. `Seq.groupBy` 튜플, 여기서 각 튜플의 첫 번째 요소는 키가 고 두 번째는 해당 키를 생성 하는 요소의 시퀀스의 시퀀스를 반환 합니다.

다음 코드 예제에서는 사용을 보여 줍니다. `Seq.groupBy` 100부터 1 까지의 숫자 시퀀스 키 값이 각각 0, 1 및 2 3 개의 그룹으로 분할 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

출력은 다음과 같습니다.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

호출 하 여 중복 요소를 제거 하는 시퀀스를 만들 수 [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)합니다. 사용할 수 있습니다 또는 [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), 각 요소에 대해 호출 되는 키 생성 함수입니다. 결과 시퀀스; 고유 키가 원래 시퀀스의 요소를 포함 합니다. 이전 요소에 중복 키를 생성 하는 요소는 무시 됩니다.

다음 코드 예제에서는 `Seq.distinct`합니다. `Seq.distinct` 이진 숫자를 나타내는 시퀀스를 생성 한 다음만 고유 요소가 0과 1을 표시 하 여 표시 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

다음 코드에서는 `Seq.distinctBy` 양수 및 음수를 포함 하는 시퀀스를 시작 하 고 키 생성 함수도 절대 값 함수를 사용 하 여 합니다. 결과 시퀀스에 음수 시퀀스 앞에 같은 절대 있는 양수 대신 선택 되어 있기 때문에 음수 시퀀스에서 일치 하는 모든 양수 없습니다. 값 또는 키입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]
    
## <a name="readonly-and-cached-sequences"></a>읽기 전용 및 캐시 된 시퀀스
[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) 시퀀스의 읽기 전용 복사본을 만듭니다. `Seq.readonly` 읽기 / 쓰기 컬렉션, 배열 등과 같이 있고 원래 컬렉션을 수정 하지 않을 때 유용 합니다. 이 함수는 데이터 캡슐화를 유지 데 사용할 수 있습니다. 다음 코드 예제에서는 배열이 포함 된 형식이 만들어집니다. 속성을 노출 하 여 배열에 있지만 사용 하 여 배열에서 만든 하는 시퀀스를 반환 배열을 반환 하는 대신 `Seq.readonly`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) 시퀀스의 저장 된 버전을 만듭니다. 사용 하 여 `Seq.cache` 때를 방지 하려면 재평가 또는 시퀀스의 시퀀스를 사용 하는 여러 스레드를 가질 수 있지만 각 요소에 한 번만 대상이 되는 있는지 확인 해야 합니다. 여러 스레드에서 사용 되는 시퀀스에 있으면를 열거 하 고 원래 순서에 대 한 값을 계산 하는 스레드 하나를 사용할 수 있습니다 및 나머지 스레드 캐시 된 시퀀스를 사용할 수 있습니다.


## <a name="performing-computations-on-sequences"></a>시퀀스에 대 한 계산 수행
단순 산술 연산에는 목록의 것과 같은 같은 [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)등입니다.

[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), 및 [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) 목록에 사용할 수 있는 해당 함수 처럼 됩니다. 시퀀스는 지원을 나열 하는 이러한 함수의 모든 변형의 하위 집합을 지원 합니다. 자세한 내용 및 예제에 대 한 참조 [나열](lists.md)합니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[F# 형식](fsharp-types.md)
