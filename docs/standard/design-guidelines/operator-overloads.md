---
title: 연산자 오버로드
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 747fc21aceae60e362c72391ae265e45d6f8445f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="operator-overloads"></a>연산자 오버로드
연산자 오버 로드에는 것 처럼 기본 제공 언어 기본 형식 표시 프레임 워크 형식을 허용 합니다.  
  
 허용 되 고 일부 경우에 유용 하지만 연산자 오버 로드를 신중 하 게 사용 해야 합니다. In 연산자는 오버 로드에 되었습니다 악용, 프레임 워크 디자이너는 간단한 방법이 되어야 하는 작업에 대 한 연산자를 사용 하기 시작 하는 경우와 같은 많은 경우가 있습니다. 다음 지침을 시기 및 연산자 오버 로드를 사용 하는 방법을 결정 하는 데 수 해야 합니다.  
  
 **하지 말고 X** 기본 (기본 제공) 형식 느낌을 해야 하는 형식을 제외 하 고 연산자 오버 로드를 정의 합니다.  
  
 **✓ 고려** 기본 형식 처럼 있어야 하는 형식에서 연산자 오버 로드를 정의 합니다.  
  
 예를 들어 <xref:System.String?displayProperty=nameWithType> 가 `operator==` 및 `operator!=` 정의 합니다.  
  
 **✓ 않습니다** 번호를 나타내는 구조체에서 연산자 오버 로드를 정의 (예: <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X 하지 않으면** 연산자 오버 로드를 정의 하는 경우 간단한 수 있습니다.  
  
 연산자 오버 로드 중인 즉각적으로 드러나지 될 작업의 결과 경우에 유용 합니다. 1을 뺍니다 할 수는 의미가 예를 들어 <xref:System.DateTime> 에서 다른 `DateTime` 를 살펴보고 한 <xref:System.TimeSpan>합니다. 그러나 논리 union 연산자 union의 두 가지 데이터베이스 쿼리를 사용 하 여 또는 시프트 연산자를 사용 하 여 스트림에 쓰기 위해 적합 하지 않습니다.  
  
 **X 하지 않으면** 연산자는 오버 로드를 정의 하는 형식은 피연산자 중 하나 이상을 아닌 경우 오버 로드를 제공 합니다.  
  
 **✓ 않습니다** 대칭 방식에서 연산자를 오버 로드 합니다.  
  
 예를 들어 오버 로드는 `operator==`, 연산자도 오버 로드 해야는 `operator!=`합니다. 마찬가지로, 재정의 한 경우는 `operator<`, 연산자도 오버 로드 해야는 `operator>`등입니다.  
  
 **✓ 고려** 각 오버 로드 된 연산자에 해당 하는 이름을 가진 메서드를 제공 합니다.  
  
 일반적인 언어 연산자 오버 로드를 지원 하지 않습니다. 연산자 오버 로드 하는 형식을 포함 동일한 기능을 제공 하는 적절 한 도메인별 이름을 보조 메서드는 것이 좋습니다.  
  
 다음 표에서 연산자와 해당 하는 친숙 한 메서드 이름이의 목록을 포함합니다.  
  
|C# 연산자 기호|메타 데이터 이름|이름|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a>연산자를 오버 로드 = =  
 오버 로드 `operator ==` 은 매우 복잡 합니다. 연산자의 의미 체계와 같은 몇 가지 다른 멤버와 호환 되도록 할 <xref:System.Object.Equals%2A?displayProperty=nameWithType>합니다.  
  
### <a name="conversion-operators"></a>변환 연산자  
 변환 연산자는 다른 한 형식에서 변환할 수 있는 단항 연산자입니다. 연산자는 피연산자 또는 반환 형식에 정적 멤버로 정의 되어야 합니다. 변환 연산자의 두 가지: 명시적 및 암시적입니다.  
  
 **X 하지 않으면** 이러한 변환의 최종 사용자가 예상 되는 것은 명확 하 게 경우 변환 연산자를 제공 합니다.  
  
 **X 하지 않으면** 형식의 도메인 외부에서 변환 연산자를 정의 합니다.  
  
 예를 들어 <xref:System.Int32>, <xref:System.Double>, 및 <xref:System.Decimal> 은 모든 숫자 형식 이지만 <xref:System.DateTime> 않습니다. 따라서 없어야 없는 변환 연산자를 한 `Double(long)` 에 `DateTime`합니다. 이러한 경우에는 생성자는 것이 좋습니다.  
  
 **X 하지 않으면** 변환이 손실 될 수 있는 경우에 암시적 변환 연산자를 제공 합니다.  
  
 예를 들어 있으면 안에서 암시적 변환이 `Double` 를 `Int32` 때문에 `Double` 더 보다 넓은 범위의 `Int32`합니다. 명시적 변환 연산자는 변환이 손실 될 수 있는 경우에 제공 될 수 있습니다.  
  
 **X 하지 않으면** 암시적 캐스트에서 예외를 throw 합니다.  
  
 변환을 수행 되 고 알 수 때문에 발생 하는 작업을 이해 하는 최종 사용자에 대 한 매우 어렵습니다.  
  
 **✓ 않습니다** throw <xref:System.InvalidCastException?displayProperty=nameWithType> 하면 캐스트 연산자에 대 한 호출 손실 변환와 연산자의 계약 손실 변환을 허용 하지 않습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
