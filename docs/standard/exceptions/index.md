---
title: "예외 처리 및 Throw | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: c3b47e61da914ebbe1106fcf45465a13b0521bb4
ms.lasthandoff: 04/08/2017

---
# <a name="handling-and-throwing-exceptions"></a>예외 처리 및 Throw
<a name="top"></a> 응용 프로그램은 실행 중에 발생하는 오류를 일관된 방식으로 처리할 수 있어야 합니다. 공용 언어 런타임에서는 일관된 방식으로 응용 프로그램에 오류를 알리기 위한 모델을 제공합니다. 모든 .NET Framework 작업은 예외를 throw하여 오류를 나타냅니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [.NET Framework의 예외](#exceptions_in_the_net_framework)  
  
-   [예외 대 일반적인 오류 처리 방법](#exceptions_vs_traditional_errorhandling_methods)  
  
-   [런타임에서 예외를 관리하는 방법](#how_the_runtime_manages_exceptions)  
  
-   [런타임 예외 필터링](#filtering_runtime_exceptions)  
  
-   [관련 항목](#related_topics)  
  
-   [참조](#reference)  
  
<a name="exceptions_in_the_net_framework"></a>   
## <a name="exceptions-in-the-net-framework"></a>.NET Framework의 예외  
 예외란 프로그램 실행 중 발생한 모든 오류 상태 또는 예기치 못한 동작입니다. 예외는 사용 중인 코드 또는 호출한 코드(예: 공유 라이브러리)의 오류, 사용 불가능한 운영 체제 리소스, 공용 언어 런타임에서 발생한 예기치 못한 상황(예: 확인할 수 없는 코드) 등에 의해 발생할 수 있습니다. 사용 중인 응용 프로그램이 이러한 일부 상황으로부터 복구될 수 있지만 복구될 수 없는 경우도 있습니다. 대부분의 응용 프로그램 예외로부터는 복구할 수 있지만 대부분의 런타임 예외로부터는 복구할 수 없습니다.  
  
 .NET Framework에서 예외는 <xref:System.Exception?displayProperty=fullName> 클래스에서 상속하는 개체입니다. 예외는 문제가 발생한 코드 영역에서 throw됩니다. 예외는 응용 프로그램에서 해당 예외를 처리하거나 프로그램이 종료될 때까지 스택으로 전달됩니다.  
  
 [맨 위로 이동](#top)  
  
<a name="exceptions_vs_traditional_errorhandling_methods"></a>   
## <a name="exceptions-vs-traditional-error-handling-methods"></a>예외 대 일반적인 오류 처리 방법  
 일반적으로 언어 오류 처리 모델은 오류를 감지하고 해당 오류 처리기를 찾는 언어 고유의 방식에 의존하거나 운영 체제에서 제공하는 오류 처리 메커니즘에 의존했습니다. 런타임에서는 다음과 같은 기능을 사용하여 예외 처리를 구현합니다.  
  
-   예외를 생성하는 언어 또는 예외를 처리하는 언어와 관계없이 예외를 처리합니다.  
  
-   예외 처리에 특정한 언어 구문이 필요하지는 않지만, 각 언어에서 고유한 구문을 정의할 수 있도록 허용합니다.  
  
-   프로세스에 그리고 컴퓨터 경계에도 예외가 throw되도록 허용합니다.  
  
 예외는 반환 코드와 같은 다른 오류 알림 방법에 비해 여러 가지 이점을 제공합니다. 오류를 그냥 지나치지 않습니다. 잘못된 값이 시스템을 통해 계속 전파되지 않습니다. 반환 코드를 확인할 필요가 없습니다. 예외 처리 코드를 쉽게 추가하여 프로그램 안정성을 높일 수 있습니다. 마지막으로 런타임의 예외 처리는 Windows 기반 C++ 오류 처리보다 더 빠릅니다.  
  
 실행 스레드가 관리 코드 블록 및 비관리 코드 블록을 정기적으로 트래버스하기 때문에 런타임은 관리 코드 또는 비관리 코드에서 예외를 throw 또는 catch할 수 있습니다. 비관리 코드에는 C++ 스타일 SEH 예외와 COM 기반 HRESULTS가 모두 포함될 수 있습니다.  
  
<a name="how_the_runtime_manages_exceptions"></a>   
## <a name="how-the-runtime-manages-exceptions"></a>런타임에서 예외를 관리하는 방법  
 런타임에서는 예외 개체 및 보호된 코드 블록을 기반으로 하는 예외 처리 모델을 사용합니다. <xref:System.Exception> 개체는 예외가 발생할 때 예외를 나타내기 위해 생성됩니다.  
  
 런타임에서는 각 실행 파일의 예외 정보 테이블을 만듭니다. 실행 파일의 각 메서드에는 예외 정보 테이블의 연결된 예외 처리 정보 배열(비어 있을 수 있음)이 있습니다. 배열의 각 항목은 보호된 코드 블록, 해당 코드와 연결된 예외 필터, 예외 처리기(`catch` 문)를 설명합니다. 이 예외 테이블은 매우 효율적이어서 예외가 발생하지 않은 경우에는 프로세서 시간 또는 메모리 사용에 대한 성능에 영향을 주지 않습니다. 즉, 예외가 발생할 때에만 리소스를 사용합니다.  
  
 예외 정보 테이블에는 보호된 블록에 대한 네 가지 유형의 예외 처리기가 있습니다.  
  
-   블록 종료가 일반적인 제어 흐름 때문에 발생했는지 처리되지 않는 예외 때문에 발생했는지 상관없이 블록이 종료될 때마다 실행되는 `finally` 처리기  
  
-   예외가 발생하는 경우에는 실행되어야 하고 일반적인 제어 흐름의 완료 시에는 실행되지 않는 오류 처리기  
  
-   지정한 클래스의 예외 또는 파생된 해당 클래스의 예외를 처리하는 형식 필터 처리기  
  
-   연결된 처리기로 예외를 처리해야 하는지 보호된 다음 블록으로 예외를 전달해야 하는지를 판단하기 위해 사용자 지정 코드를 실행하는 사용자 필터 처리기  
  
 각 언어는 해당 사양에 따라 이러한 예외 처리기를 구현합니다. 예를 들어 Visual Basic에서는 `catch` 문에 `When` 키워드를 사용하여 변수를 비교함으로써 사용자 필터 처리기에 대한 액세스를 제공합니다. C#에서는 사용자 필터 처리기를 구현하지 않습니다.  
  
 예외가 발생하면 런타임은 다음과 같은 두 단계의 프로세스를 시작합니다.  
  
1.  런타임에서는 다음을 수행하는 첫 번째 보호된 블록 배열을 검색합니다.  
  
    -   현재 실행되고 있는 명령이 포함된 영역을 보호합니다.  
  
    -   예외 처리기를 포함하거나 예외를 처리하는 필터를 포함합니다.  
  
2.  검색 결과 일치하는 내용이 있으면 런타임은 예외를 설명하는 <xref:System.Exception> 개체를 만듭니다. 그런 다음 런타임은 예외가 발생한 문과 예외를 처리하는 문 사이의 모든 `finally` 또는 오류 문을 실행합니다. 예외 처리기의 순서가 중요합니다. 가장 안쪽에 있는 예외 처리기가 제일 먼저 평가됩니다. 또한 예외 처리기는 예외를 catch한 루틴의 지역 변수와 로컬 메모리에 액세스할 수 있지만 예외가 throw되는 시점에서의 중간 값은 손실됩니다.  
  
     검색 결과 현재 메서드에 일치하는 내용이 없으면 런타임은 현재 메서드의 각 호출자를 검색하여 이러한 과정을 스택까지 계속 진행합니다. 일치하는 호출자가 없는 경우 런타임은 디버거에서 예외에 액세스할 수 있도록 합니다. 디버거가 예외에 연결되지 않으면 런타임에서 <xref:System.AppDomain.UnhandledException?displayProperty=fullName> 이벤트를 발생합니다. 이 이벤트에 대한 수신기가 없는 경우 런타임은 스택 추적을 덤프하고 응용 프로그램을 끝냅니다.  
  
 [맨 위로 이동](#top)  
  
<a name="filtering_runtime_exceptions"></a>   
## <a name="filtering-runtime-exceptions"></a>런타임 예외 필터링  
 형식별로 또는 일부 사용자 정의 기준별로 catch 및 처리하는 예외를 필터링할 수 있습니다.  
  
 형식 필터 처리기는 특정 형식의 예외 또는 이 예외에서 파생된 클래스를 관리합니다. 다음 예제에서는 특정 예외, 여기서는 <xref:System.IO.FileNotFoundException>이라는 예외를 catch하기 위해 디자인된 형식 필터 처리기를 보여 줍니다.  
  
 [!code-cpp[CatchException#5](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception3.cpp#5)]
 [!code-csharp[CatchException#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception3.cs#5)]
 [!code-vb[CatchException#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception3.vb#5)]  
  
 사용자 필터 예외 처리기는 예외에 대해 정의한 요구 사항을 기반으로 하여 예외를 catch하고 처리합니다. 이러한 방식으로 예외를 필터링하는 방법에 대한 자세한 내용은 [Catch 블록에 특정 예외 사용](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)을 참조하세요.  
  
 [맨 위로 이동](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[Exception 클래스 및 속성](../../../docs/standard/exceptions/exception-class-and-properties.md)|예외 개체의 요소를 설명합니다.|  
|[예외 계층](../../../docs/standard/exceptions/exception-hierarchy.md)|대부분의 예외가 파생된 예외에 대해 설명합니다.|  
|[예외 처리 기본 사항](../../../docs/standard/exceptions/exception-handling-fundamentals.md)|catch, throw 및 finally 문을 사용하여 예외를 처리하는 방법에 대해 설명합니다.|  
|[예외에 대한 모범 사례](../../../docs/standard/exceptions/best-practices-for-exceptions.md)|최선의 예외 처리 방법을 제안하고 설명합니다.|  
|[COM Interop 예외 처리](../../../docs/standard/exceptions/handling-com-interop-exceptions.md)|비관리 코드에서 throw되고 catch되는 예외를 처리하는 방법에 대해 설명합니다.|  
|[방법: HRESULT 및 예외 매핑](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|관리 코드 및 비관리 코드 사이에 예외를 매핑하는 방법에 대해 설명합니다.|  
  
<a name="reference"></a>   
## <a name="reference"></a>참조  
 <xref:System.Exception?displayProperty=fullName>  
  
 <xref:System.ApplicationException?displayProperty=fullName>  
  
 <xref:System.SystemException?displayProperty=fullName>
