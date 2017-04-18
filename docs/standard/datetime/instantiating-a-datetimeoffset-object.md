---
title: "DateTimeOffset 개체 인스턴스화 | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "표준 시간대 개체 인스턴스화"
  - "표준 시간대 개체[.NET Framework], 인스턴스화"
  - "DateTimeOffset 구조, DateTime으로 변환"
  - "DateTimeOffset 구조, 인스턴스화"
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# DateTimeOffset 개체 인스턴스화
<xref:System.DateTimeOffset> 구조체는 <xref:System.DateTimeOffset> 값을 만들 수 있는 여러 가지 방법을 제공합니다.  이러한 방법은 각각 해당 메서드를 통해 새 <xref:System.DateTime> 값을 인스턴스화하는 것이며 UTC\(협정 세계시\)의 날짜 및 시간 값 오프셋을 지정할 수 있도록 향상되었습니다.  특히, 다음과 같은 방법으로 <xref:System.DateTimeOffset> 값을 인스턴스화할 수 있습니다.  
  
-   날짜 및 시간 리터럴 사용  
  
-   <xref:System.DateTimeOffset> 생성자 호출  
  
-   값을 <xref:System.DateTimeOffset> 값으로 암시적으로 변환  
  
-   날짜 및 시간의 문자열 표현 구문 분석  
  
 이 항목에서는 새 <xref:System.DateTimeOffset> 값을 인스턴스화하는 이러한 메서드에 대한 자세한 설명과 코드 예제를 제공합니다.  
  
## 날짜 및 시간 리터럴  
 날짜 및 시간 리터럴을 지원하는 언어의 경우 <xref:System.DateTime> 값을 인스턴스화하는 가장 일반적인 방법 중 하나는 날짜와 시간을 하드 코딩된 리터럴 값으로 제공하는 것입니다.  예를 들어, 다음 Visual Basic 코드에서는 값이 January 1, 2008, at 10:00 AM인 <xref:System.DateTime> 개체를 만듭니다.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]  
  
 <xref:System.DateTimeOffset> 값은 <xref:System.DateTime> 리터럴을 지원하는 언어를 사용할 때 날짜 및 시간 리터럴을 사용하여 초기화할 수도 있습니다.  예를 들어, 다음 Visual Basic 코드에서는 <xref:System.DateTimeOffset> 개체를 만듭니다.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]  
  
 콘솔 출력에서 볼 수 있듯이 이 방법으로 만든 <xref:System.DateTimeOffset> 값에는 현지 표준 시간대의 오프셋이 할당됩니다.  즉, 코드가 다른 컴퓨터에서 실행될 경우 문자 리터럴을 사용하여 할당한 <xref:System.DateTimeOffset> 값이 특정 시간을 식별하지 않습니다.  
  
## DateTimeOffset 생성자  
 <xref:System.DateTimeOffset> 형식은 여섯 개의 생성자를 정의합니다.  이중 네 개는 UTC에서의 날짜 및 시간 오프셋을 정의하는 <xref:System.TimeSpan> 형식의 추가 매개 변수가 있는 <xref:System.DateTime> 생성자에 직접 해당합니다.  이러한 생성자를 사용하면 개별 날짜 및 시간 구성 요소의 값을 기반으로 <xref:System.DateTimeOffset> 값을 정의할 수 있습니다.  예를 들어, 다음 코드에서는 이러한 네 생성자를 사용하여 값이 모두 7\/1\/2008 12:05 AM \+01:00로 동일한 <xref:System.DateTimeOffset> 개체를 인스턴스화합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]  
  
 <xref:System.Globalization.PersianCalendar> 개체를 해당 생성자에 대한 인수 중 하나로 사용하여 인스턴스화한 <xref:System.DateTimeOffset> 개체의 값은 콘솔에 표시될 때 페르시아력이 아니라 그레고리오력 날짜로 표시됩니다.  페르시아력을 사용하여 날짜를 출력하려면 <xref:System.Globalization.PersianCalendar> 항목의 예제를 참조하십시오.  
  
 나머지 두 생성자는 <xref:System.DateTime> 값을 사용하여 <xref:System.DateTimeOffset> 개체를 만듭니다.  이중 첫 번째 생성자는 <xref:System.DateTimeOffset> 값으로 변환할 <xref:System.DateTime> 값인 단일 매개 변수를 갖습니다.  결과 <xref:System.DateTimeOffset> 값의 오프셋은 이 생성자의 단일 매개 변수에 대한 <xref:System.DateTime.Kind%2A> 속성에 따라 달라집니다.  이 값이 <xref:System.DateTimeKind?displayProperty=fullName>이면 오프셋은 <xref:System.TimeSpan.Zero?displayProperty=fullName>와 같게 설정됩니다.  그렇지 않으면 현지 표준 시간대의 오프셋과 같게 설정됩니다.  다음 예제에서는 이 생성자를 사용하여 UTC 및 현지 표준 시간대를 나타내는 <xref:System.DateTimeOffset> 개체를 인스턴스화하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]  
  
> [!NOTE]
>  단일 <xref:System.DateTime> 매개 변수가 있는 <xref:System.DateTimeOffset> 생성자의 오버로드를 호출하는 것은 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값으로 암시적으로 변환하는 것과 같습니다.  
  
 <xref:System.DateTime> 값을 사용하여 <xref:System.DateTimeOffset> 개체를 만드는 두 번째 생성자는 두 개의 매개 변수, 변환할 <xref:System.DateTime> 값 및 UTC에서의 날짜 및 시간 오프셋을 나타내는 <xref:System.TimeSpan> 값을 갖습니다.  이 오프셋 값은 이 생성자의 첫 번째 매개 변수에 대한 <xref:System.DateTime.Kind%2A> 속성과 일치해야 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.  첫 번째 매개 변수의 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>이면 두 번째 매개 변수의 값은 <xref:System.TimeSpan.Zero?displayProperty=fullName>여야 합니다.  첫 번째 매개 변수의 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>이면 두 번째 매개 변수의 값은 로컬 시스템의 표준 시간대 오프셋이어야 합니다.  첫 번째 매개 변수의 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>이면 오프셋은 임의의 유효한 값일 수 있습니다.  다음 코드에서는 이 생성자를 호출하여 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값으로 변환하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]  
  
## 암시적 형식 변환  
 <xref:System.DateTimeOffset> 형식은 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값으로 변환하는 한 가지 암시적 형식 변환을 지원합니다. 암시적 형식 변환은 명시적 캐스트\(C\#의 경우\) 또는 변환\(Visual Basic의 경우\)이 필요하지 않고 정보가 손실되지 않는, 한 형식에서 다른 형식으로의 변환입니다.  이 형식에서는 다음과 같은 코드를 사용할 수 있습니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]  
  
 결과 <xref:System.DateTimeOffset> 값의 오프셋은 <xref:System.DateTime.Kind%2A?displayProperty=fullName> 속성 값에 따라 달라집니다.  이 값이 <xref:System.DateTimeKind?displayProperty=fullName>이면 오프셋은 <xref:System.TimeSpan.Zero?displayProperty=fullName>와 같게 설정됩니다.  이 값이 <xref:System.DateTimeKind?displayProperty=fullName> 또는 <xref:System.DateTimeKind?displayProperty=fullName>이면 오프셋은 현지 표준 시간대의 오프셋과 같게 설정됩니다.  
  
## 날짜 및 시간의 문자열 표현 구문 분석  
 <xref:System.DateTimeOffset> 형식은 날짜 및 시간의 문자열 표현을 <xref:System.DateTimeOffset> 값으로 변환할 수 있는 다음과 같은 네 개의 메서드를 지원합니다.  
  
-   <xref:System.DateTimeOffset.Parse%2A>는 날짜 및 시간의 문자열 표현을 <xref:System.DateTimeOffset> 값으로 변환하려고 하고 변환이 실패할 경우 예외를 throw합니다.  
  
-   <xref:System.DateTimeOffset.TryParse%2A>는 날짜 및 시간의 문자열 표현을 <xref:System.DateTimeOffset> 값으로 변환하려고 하고 변환이 실패할 경우 `false`를 반환합니다.  
  
-   <xref:System.DateTimeOffset.ParseExact%2A>는 특정 형식의 날짜 및 시간의 문자열 표현을 <xref:System.DateTimeOffset> 값으로 변환하려고 하고  변환이 실패할 경우 예외를 throw합니다.  
  
-   <xref:System.DateTimeOffset.TryParseExact%2A>는 특정 형식의 날짜 및 시간의 문자열 표현을 <xref:System.DateTimeOffset> 값으로 변환하려고 하고  변환이 실패할 경우 `false`를 반환합니다.  
  
 다음 예제에서는 이러한 네 개의 문자열 변환 메서드를 각각 호출하여 <xref:System.DateTimeOffset> 값을 인스턴스화하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)