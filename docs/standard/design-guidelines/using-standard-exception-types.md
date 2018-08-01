---
title: 표준 예외 형식 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81e4047c171e3a58f335821d64390432524b25df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574597"
---
# <a name="using-standard-exception-types"></a>표준 예외 형식 사용
이 섹션에서는 프레임 워크 및 사용 세부 정보에서 제공 하는 표준 예외를 설명 합니다. 목록 완전 한 목록이 되지는 않습니다. 다른 프레임 워크 예외 형식의 사용에 대 한.NET Framework 참조 설명서를 참조 하십시오.  
  
## <a name="exception-and-systemexception"></a>예외 및 SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> 또는 <xref:System.SystemException?displayProperty=nameWithType>합니다.  
  
 **X DO NOT** catch `System.Exception` 또는 `System.SystemException` 프레임 워크 코드에 다시 throw 하려는 경우가 아니면 합니다.  
  
 **X AVOID** 위해서 `System.Exception` 또는 `System.SystemException`, 최상위 예외 처리기에서를 제외 하 고 있습니다.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw 하거나이 로부터 파생할 <xref:System.ApplicationException>합니다.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** throw 한 <xref:System.InvalidOperationException> 부적절 한 상태에 개체가 있으면 됩니다.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException, 및 ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> 또는 멤버에 잘못 된 인수가 전달 되 면 그 하위 중 하나입니다. 해당 하는 경우에 가장 많이 파생 된 예외 형식이 선호 합니다.  
  
 **✓ DO** 설정는 `ParamName` 속성의 서브 클래스 중 하나를 throw 할 때 `ArgumentException`합니다.  
  
 이 속성은 예외를 throw를 발생 시킨 매개 변수의 이름을 나타냅니다. 생성자 오버 로드 중 하나를 사용 하 여 속성을 설정할 수 있는 참고 합니다.  
  
 **✓ DO** 사용 `value` 속성 setter의 암시적 값 매개 변수 이름에 대 한 합니다.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException, 및 AccessViolationException  
 **X DO NOT** 공개적으로 호출할 수 Api 명시적 또는 암시적으로 throw 할 수 있도록 <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, 또는 <xref:System.IndexOutOfRangeException>합니다. 이러한 예외 예약 된 페이지와 실행 엔진에 의해 throw 및 대부분의 경우 버그를 나타냅니다.  
  
 인수 이러한 예외를 throw 되지 않도록 하려면 검사를 수행 합니다. 시간이 지남에 따라 변경 될 수 있는 방법의 구현 세부 정보를 노출 이러한 예외를 throw 합니다.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** 명시적으로 throw <xref:System.StackOverflowException>합니다. CLR에 의해서만 예외를 명시적으로 throw 해야 합니다.  
  
 **X DO NOT** catch `StackOverflowException`합니다.  
  
 임의의 스택 오버플로 있는 경우 일관성을 유지 관리 되는 코드를 작성할 거의 불가능 합니다. CLR의 관리 되지 않는 부분에서 임의의 스택 오버플로 철회 하는 대신 스택이 오버플로 잘 정의 된 위치로 이동 하는 프로브를 사용 하 여 일관성을 유지 합니다.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** 명시적으로 throw <xref:System.OutOfMemoryException>합니다. 이 예외는 CLR 인프라에서만 throw 됩니다.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException, SEHException, 및 ExecutionEngineException  
 **X DO NOT** 명시적으로 throw <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, 및 <xref:System.Runtime.InteropServices.SEHException>합니다. 이러한 예외는 CLR 인프라에서만 throw 됩니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [예외 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)
