---
title: Like 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: a9c672a397510c69c9ee67358689feff80d8831a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605422"
---
# <a name="like-operator-visual-basic"></a>Like 연산자(Visual Basic)
문자열을 패턴과 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수. 모든 `Boolean` 변수입니다. 결과 한 `Boolean` 나타내는 값 여부는 `string` 충족는 `pattern`합니다.  
  
 `string`  
 필수. 임의의 `String` 식입니다.  
  
 `pattern`  
 필수. 모든 `String` "주의"에 설명 된 패턴 일치 규칙에 맞는 식  
  
## <a name="remarks"></a>설명  
 경우에 값 `string` 에 포함 된 패턴을 충족 `pattern`, `result` 은 `True`합니다. 문자열 패턴을 충족 하지 못하는 경우 `result` 은 `False`합니다. 두 `string` 및 `pattern` 빈 문자열이 결과 `True`합니다.  
  
## <a name="comparison-method"></a>비교 메서드  
 동작은 `Like` 연산자에 따라 달라 집니다는 [옵션 비교 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다. 각 소스 파일에 대 한 기본 문자열 비교 메서드는 `Option Compare Binary`합니다.  
  
## <a name="pattern-options"></a>패턴 옵션  
 기본 제공 패턴 일치 문자열 비교에 유용한 도구를 제공 합니다. 패턴 일치 기능을 사용 하면 각 문자에 맞게 `string` 특정 문자, 와일드 카드 문자, 문자 목록, 또는 문자 범위에 대 한 합니다. 다음 표에서 허용 되는 문자를 보여 줍니다. `pattern` 일치 하 고 있습니다.  
  
|문자 `pattern`|에 일치 하는 `string`|  
|-----------------------------|-------------------------|  
|`?`|단일 문자|  
|`*`|0 개 이상의 문자|  
|`#`|임의의 단일 숫자 (0-9)|  
|`[charlist]`|단일 문자 `charlist`|  
|`[!charlist]`|에 없는 모든 단일 문자 `charlist`|  
  
## <a name="character-lists"></a>문자 목록  
 하나 이상의 문자 그룹 (`charlist`) 대괄호로 묶은 (`[ ]`)는 내 임의의 단일 문자와 일치 하는 데 사용할 수 `string` 숫자를 포함 하 여 거의 모든 문자 코드를 포함할 수 있습니다.  
  
 느낌표 (`!`) 맨 앞에 `charlist` 경우의 문자를 제외한 모든 문자는 일치 하는 내용을 의미 `charlist` 에 `string`합니다. 를 대괄호 외부에서 사용 하는 경우 자체에서 느낌표를 찾습니다.  
  
## <a name="special-characters"></a>특수 문자  
 특수 문자 왼쪽된 대괄호에 맞게 (`[`), 물음표 (`?`), 숫자 기호 (`#`), 별표 (`*`), 대괄호로 묶습니다. 오른쪽 대괄호 (`]`) 자신과 일치 하는 그룹 내에서 사용할 수 없습니다 되지만 개별 문자로 그룹 외부에 있는 사용 될 수 있습니다.  
  
 문자 시퀀스 `[]` 길이가 0 인 문자열로 간주 됩니다 (`""`). 그러나 대괄호로 묶은 문자 목록의 일부가 될 수 없습니다. 에 위치 하는지 여부를 확인 하려는 경우 `string` 하나가 포함 된 문자 또는 모두에 문자가 그룹에서 사용할 수 있습니다 `Like` 두 번입니다. 예를 들어 참조 [하는 방법: 패턴에 대해 문자열](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)합니다.  
  
## <a name="character-ranges"></a>문자 범위  
 하이픈을 사용 하 여 (`–`)를 하 한과 상한을 범위를 구분 하려면 `charlist` 문자 범위를 지정할 수 있습니다. 예를 들어 `[A–Z]` 해당 문자에 위치 하는 경우 일치 결과가 `string` 범위 내 모든 문자를 포함 `A`–`Z`, 및 `[!H–L]` 해당 문자 위치 하는 경우에 일치 하는 항목에 발생 합니다. 범위 밖에 있는 경우 모든 문자를 포함 `H`–`L`합니다.  
  
 문자 범위를 지정 하면 오름차순 정렬 순서, 즉, 오름차순으로 나타나야 합니다. 따라서 `[A–Z]` 올바른 패턴은 있지만 `[Z–A]` 않습니다.  
  
### <a name="multiple-character-ranges"></a>여러 문자 범위  
 동일한 문자 위치에 대 한 여러 범위를 지정 하려면 대괄호 구분 기호 없이 내에 추가 합니다. 예를 들어 `[A–CX–Z]` 해당 문자에 위치 하는 경우 일치 결과가 `string` 중 하나가 범위 내 모든 문자를 포함 `A`–`C` 또는 범위의 `X`–`Z`합니다.  
  
### <a name="usage-of-the-hyphen"></a>하이픈 사용  
 하이픈 (`–`) (느낌표, 있는 경우) 한 후 시작 또는 끝날 때 나타날 수 있습니다 `charlist` 자체와 일치 하도록 합니다. 다른 위치에 있는 하이픈 문자를 하이픈의 어느 쪽에 있는 문자의 범위를 식별 합니다.  
  
## <a name="collating-sequence"></a>데이터 정렬 순서  
 지정 된 범위의 의미 문자에서 런타임에 의해 결정 된 순서에 따라 달라 집니다 `Option``Compare` 시스템의 로캘 설정 코드에서 실행 되 고 있습니다. 와 `Option``Compare``Binary`, 범위 `[A–E]` 일치 `A`, `B`, `C`, `D`, 및 `E`합니다. 와 `Option``Compare``Text`, `[A–E]` 일치 `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, 및 `e`합니다. 범위 일치 하지 않습니다. `Ê` 또는 `ê` 악센트 문자 악센트가 없는 문자 정렬 순서에서 다음 collate 때문에 있습니다.  
  
## <a name="digraph-characters"></a>Digraph 문자  
 일부 언어에서 두 개의 별도 문자를 나타내는 알파벳 문자가 있습니다. 여러 언어 문자를 사용 하는 예를 들어 `æ` 문자를 나타내는 `a` 및 `e` 함께 표시 되는 경우. `Like` 연산자 인식 digraph 문자 및 두 개의 개별 문자는 동일 합니다.  
  
 Digraph 문자 중 하나에 있는 경우, digraph 문자를 사용 하는 언어 시스템 로캘 설정에 지정 된 경우 `pattern` 또는 `string` 다른 문자열에 해당 하는 두 문자 시퀀스와 일치 합니다. 마찬가지로,의 digraph 문자 `pattern` 대괄호로 묶은 자체적으로, 목록, 또는 범위에 해당 하는 두 문자 시퀀스와 일치 `string`합니다.  
  
## <a name="overloading"></a>오버로딩  
 `Like` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `Like` 다양 한 패턴 문자열을 비교 하는 연산자입니다. 결과 다루지는 `Boolean` 각 문자열 패턴을 충족 하는지 여부를 나타내는 변수입니다.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [방법: 패턴에 대해 문자열 비교](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
