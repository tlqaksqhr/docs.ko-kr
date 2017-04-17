---
title: "연산자 오버 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "오버 로드 연산자 [.NET Framework]"
  - "이름 [.NET Framework] 오버 로드 된 연산자"
  - "멤버 디자인 지침, 연산자"
  - "오버로드된 연산자"
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 연산자 오버 로드
프레임 워크 형식을 것 처럼 기본 제공 언어 기본 형식 표시를 허용 하는 연산자 오버 로드.  
  
 허용 되 고 일부 경우에 유용 하지만 연산자 오버 로드를 신중 하 게 사용 해야 합니다. 연산자의 오버 로드는 되었습니다 악용, 프레임 워크 디자이너는 간단한 방법을 해야 하는 작업에 대 한 연산자를 사용 하 여 시작 하는 때와 같은 많은 경우가 있습니다. 연산자 오버 로드를 사용 하 여 방법과 시기를 결정 합니다. 다음 지침 도움이 됩니다.  
  
 **X 방지** 기본 \(기본 제공\) 형식 느낌을 해야 하는 형식에서 제외 하 고 연산자 오버 로드를 정의 합니다.  
  
 **✓ 고려** 기본 형식 처럼 있어야 하는 형식에서 연산자 오버 로드를 정의 합니다.  
  
 예를 들어 <xref:System.String?displayProperty=fullName> 가 `operator==` 및 `operator!=` 정의 합니다.  
  
 **✓ 수행** 번호를 나타내는 구조체에서 연산자 오버 로드를 정의 \(예: <xref:System.Decimal?displayProperty=fullName>\).  
  
 **X 하지 않으려면** 연산자 오버 로드를 정의 하는 경우 쓴 귀여운 제 수입니다.  
  
 연산자 오버 로드는 즉시 알아낼 될 작업의 결과 경우에 유용 합니다. 예를 들어 편이 빼면 수 있으려면 <xref:System.DateTime> 에서 다른 `DateTime` 하 고는 <xref:System.TimeSpan>합니다. 그러나 논리 union 연산자 union 두 데이터베이스 쿼리를 사용 하 여 또는 스트림에 쓸 시프트 연산자를 사용 하 여 적합 하지 않습니다.  
  
 **X 하지 않으려면** 연산자 오버 로드를 정의 하는 형식 피연산자 중 하나 이상이 아닌 경우 오버 로드를 제공 합니다.  
  
 **✓ 수행** 대칭 방식에서 연산자를 오버 로드 합니다.  
  
 예를 들어, 오버 로드는 `operator==`, 오버 로드도 해야는 `operator!=`합니다. 마찬가지로, 재정의 한 경우는 `operator<`, 오버 로드도 해야는 `operator>`, 등.  
  
 **✓ 고려** 각 오버 로드 된 연산자에 해당 하는 이름을 가진 메서드를 제공 합니다.  
  
 다양 한 언어 연산자 오버 로드를 지원 하지 않습니다. 형식 연산자를 오버 로드에 동일한 기능을 제공 하는 적절 한 도메인 특정 이름 사용 하 여 보조 메서드를 포함 것이 좋습니다.  
  
 다음 표에서 연산자와 해당 하는 친숙 한 메서드 이름을의 목록이 포함 되어 있습니다.  
  
|C\# 연산자 기호|메타 데이터 이름|식별 이름|  
|----------------|---------------|-----------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|`&#124;`|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|`&#124;&#124;`|`op_LogicalOr`|`Or`|  
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
|`&#124;=`|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### 연산자 오버 로드 \= \=  
 오버 로드 `operator ==` 은 상당히 복잡 합니다. 연산자의 의미 체계와 같은 몇 가지 다른 멤버와 호환 되도록 해야 <xref:System.Object.Equals%2A?displayProperty=fullName>합니다.  
  
### 변환 연산자  
 변환 연산자는 다른 한 형식에서 변환할 수 있는 단항 연산자입니다. 연산자는 피연산자 또는 반환 형식에 정적 멤버로 정의 되어야 합니다. 변환 연산자의 두 종류가 있습니다: 명시적 및 암시적입니다.  
  
 **X 하지 않으려면** 이러한 변환을, 최종 사용자가 예상 되는 것은 명확 하 게 하는 경우에 변환 연산자를 제공 합니다.  
  
 **X 하지 않으려면** 형식의 도메인 외부의 변환 연산자를 정의 합니다.  
  
 예를 들어 <xref:System.Int32>, <xref:System.Double>, 및 <xref:System.Decimal> 는 모든 숫자 형식, 반면 <xref:System.DateTime> 않습니다. 따라서 없어야 없는 변환 연산자를 한 `Double(long)` 에 `DateTime`합니다. 생성자는 이러한 경우 기본 설정입니다.  
  
 **X 하지 않으려면** 변환이 손실 될 수 있는 경우에 암시적 변환 연산자를 제공 합니다.  
  
 예를 들어 해야 있어야에서 암시적 변환이 `Double` 를 `Int32` 때문에 `Double` 보다 더 넓은 범위 `Int32`합니다. 변환할 손실 될 수 있는 경우에 명시적 변환 연산자를 제공할 수 있습니다.  
  
 **X 하지 않으려면** 암시적 캐스트에서 예외를 throw 합니다.  
  
 최종 사용자에 게는 변환이 수행 되 고 인식 되지 않을 수도 있습니다 때문에 상황을 이해 하기 매우 어렵습니다.  
  
 **✓ 수행** throw <xref:System.InvalidCastException?displayProperty=fullName> 경우 손실 변환에는 캐스트 연산자에 대 한 호출 결과 및 연산자의 계약 손실 변환을 허용 하지 않습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)