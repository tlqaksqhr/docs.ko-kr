---
title: Access Control(F#)
description: '형식, 메서드 및 F # 프로그래밍 언어의 함수 같은 프로그래밍 요소에 대 한 액세스를 제어 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fee5f719904b61c3082d56f73448defdea39f472
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="access-control"></a>Access Control

*액세스 제어* 클라이언트 유형, 메서드 및 함수 등의 특정 프로그램 요소를 사용할 수 있는 선언 가리킵니다.


## <a name="basics-of-access-control"></a>액세스 제어 기본 사항
F #에서 액세스 제어 지정자 `public`, `internal`, 및 `private` 모듈, 형식, 메서드, 값 정의 함수, 속성 및 명시적 필드에 적용할 수 있습니다.


- `public` 모든 호출자가 엔터티를 액세스할 수 있는지를 나타냅니다.

- `internal` 엔터티는 동일한 어셈블리 에서만에서 액세스할 수 있는지를 나타냅니다.

- `private` 엔터티는 바깥쪽 형식 또는 모듈 에서만 액세스할 수 있는지를 나타냅니다.


>[!NOTE] 
액세스 지정자 `protected` 지원 않는 언어로 작성 된 형식을 사용 하는 경우 허용 되는 F #에서 사용 되지 않습니다 `protected` 액세스 합니다. 따라서 보호 된 메서드를 재정의 하는 경우 메서드에 계속 클래스 및 해당 하위 요소 내 에서만 액세스할 수 있습니다.

지정자는 경우를 제외 하 고 엔터티 이름 앞에 옵니다 일반적으로 `mutable` 또는 `inline` 지정자만 사용 되는 액세스 제어 지정자 뒤에 표시 합니다.

액세스 지정 자가 없는 사용 하는 경우 기본값은 `public`를 제외 하 고 `let` 항상 이며는 형식에 바인딩 `private` 형식으로 합니다.

F #의 시그니처는 F # 프로그램 요소에 대 한 액세스를 제어 하기 위한 다른 메커니즘을 제공 합니다. 시그니처가는 액세스 제어에 필요 하지 않습니다. 자세한 내용은 [시그니처](signatures.md)를 참조하세요.


## <a name="rules-for-access-control"></a>액세스 제어에 대 한 규칙
액세스 제어는 다음 규칙이 적용 됩니다.


- 상속 선언 (즉, 사용 `inherit` 클래스에 대 한 기본 클래스를 지정 하려면), 선언 (즉, 지정 하는 클래스 인터페이스를 구현), 인터페이스 및 추상 멤버에는 항상 바깥쪽 형식과 같은 동일한 수준의 액세스 권한이 있습니다. 따라서 이러한 구문에 대 한 액세스 제어 지정자를 사용할 수 없습니다.

- 구별된 된 공용 구조체의 개별 사례 공용 구조체 형식에서 별도 액세스 제어 한정자를 가질 수 없습니다.

- 레코드 종류의 개별 필드는 별도 레코드 종류의 액세스 제어 한정자를 가질 수 없습니다.


## <a name="example"></a>예제
다음 코드에서는 액세스 제어 지정자를 사용 합니다. 프로젝트에 두 개의 파일이 `Module1.fs` 및 `Module2.fs`합니다. 각 파일은 암시적으로 모듈. 따라서 두 개의 모듈은 `Module1` 및 `Module2`합니다. 에 개인 형식 및 내부 형식에 정의 되어 `Module1`합니다. 전용 형식에서 액세스할 수 없는 `Module2`, 뿐 아니라 내부 형식이 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
다음 코드에 만든 형식의 접근성 테스트 `Module1.fs`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[시그니처](signatures.md)
