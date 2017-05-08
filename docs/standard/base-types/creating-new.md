---
title: ".NET Framework에서 새 문자열 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Concat 메서드"
  - "CopyTo 메서드"
  - "Format 메서드"
  - "Insert 메서드"
  - "Join 메서드"
  - "문자열[.NET Framework], 만들기"
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# .NET Framework에서 새 문자열 만들기
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 단순한 할당을 사용하여 문자열을 만들 수 있고 클래스 생성자를 오버로드하여 서로 다른 여러 매개 변수를 사용한 문자열 생성을 지원할 수 있습니다.  또한 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 여러 문자열, 문자열 배열 또는 개체를 결합하여 새 문자열 개체를 만드는 여러 가지 메서드를 <xref:System.String?displayProperty=fullName> 클래스에 제공합니다.  
  
## 할당을 사용하여 문자열 만들기  
 새 <xref:System.String> 개체를 만드는 가장 쉬운 방법은 문자열 리터럴을 단순히 <xref:System.String> 개체에 할당하는 것입니다.  
  
## 클래스 생성자를 사용하여 문자열 만들기  
 <xref:System.String> 클래스 생성자의 오버로드를 사용하여 문자 배열에서 문자열을 만들 수 있습니다.  특정 문자를 지정된 횟수만큼 복제하여 새 문자열을 만들 수도 있습니다.  
  
## 문자열을 반환하는 메서드  
 다음 표에서는 새 문자열 개체를 반환하는 몇 가지 유용한 메서드를 보여 줍니다.  
  
|메서드 이름|기능|  
|------------|--------|  
|<xref:System.String.Format%2A?displayProperty=fullName>|입력 개체의 집합을 사용하여 서식 지정된 문자열을 만듭니다.|  
|<xref:System.String.Concat%2A?displayProperty=fullName>|두 개 이상의 기존 문자열을 연결하여 새 문자열을 만듭니다.|  
|<xref:System.String.Join%2A?displayProperty=fullName>|문자열 배열을 결합하여 새 문자열을 만듭니다.|  
|<xref:System.String.Insert%2A?displayProperty=fullName>|기존 문자열의 지정된 인덱스에 문자열을 삽입하여 새 문자열을 만듭니다.|  
|<xref:System.String.CopyTo%2A?displayProperty=fullName>|문자열에서 지정한 문자를 문자 배열의 지정된 위치로 복사합니다.|  
  
### 형식  
 **String.Format** 메서드를 사용하여 서식 지정된 문자열을 만들고 여러 개체를 나타내는 문자열을 연결할 수 있습니다.  이 메서드에서는 전달된 개체를 문자열로 자동 변환합니다.  예를 들어, 응용 프로그램에서 사용자에게 **Int32** 값과 **DateTime** 값을 표시해야 하는 경우 **Format** 메서드를 사용하면 간편하게 이러한 값을 표시하는 문자열을 만들 수 있습니다.  이 메서드에 적용하는 서식 지정 규칙에 대한 자세한 내용은 [합성 서식 지정](../../../docs/standard/base-types/composite-formatting.md)에 있는 관련 단원을 참조하십시오.  
  
 다음 예제에서는 **Format** 메서드를 통해 정수 변수를 사용하는 문자열을 만듭니다.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 이 예제에서 <xref:System.DateTime.Now%2A?displayProperty=fullName>는 현재 스레드에 연결된 문화권에서 지정하는 방식으로 현재 날짜와 시간을 표시합니다.  
  
### Concat  
 **String.Concat** 메서드를 사용하면 간편하게 두 개 이상의 기존 개체를 이용하여 새로운 문자열 개체를 만들 수 있습니다.  이 메서드에서는 특정 언어에 국한되지 않는 방식으로 문자열을 연결할 수 있습니다.  이 메서드는 **System.Object**에서 파생되는 모든 클래스를 받아들입니다.  다음 예제에서는 두 개의 기존 문자열 개체와 구분 문자에서 문자열을 만듭니다.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### Join  
 **String.Join** 메서드에서는 문자열 배열과 구분 기호 문자열을 받은 다음 새로운 문자열을 만듭니다.  이 메서드는 여러 개의 문자열을 연결하여 쉼표 등의 구분 기호로 분리된 문자열의 목록을 만들려는 경우에 유용합니다.  
  
 다음 예제에서는 공백을 사용하여 문자열 배열을 연결합니다.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### Insert  
 **String.Insert** 메서드를 사용하면 문자열의 지정된 위치에 다른 문자열을 삽입하여 새로운 문자열을 만들 수 있습니다.  이 메서드에서는 0에서 시작하는 인덱스를 사용합니다.  다음 예제에서는 `MyString`의 다섯 번째 인덱스 위치에 문자열을 삽입하여 새로운 문자열을 만듭니다.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### CopyTo  
 **String.CopyTo** 메서드를 사용하여 문자열의 일부분을 문자 배열에 복사할 수 있습니다.  문자열의 시작 인덱스 및 복사할 문자의 개수를 지정할 수 있습니다.  이 메서드에서는 소스 인덱스, 문자의 배열, 대상 인덱스 및 복사할 문자의 개수를 인수로 사용합니다.  모든 인덱스는 0에서 시작합니다.  
  
 다음 예제에서는 **CopyTo** 메서드를 사용하여 문자열 개체에 포함된 "Hello"라는 단어의 문자를 문자 배열의 첫 번째 인덱스 위치에 복사합니다.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## 참고 항목  
 [기본적인 문자열 작업](../../../docs/standard/base-types/basic-string-operations.md)   
 [복합 형식 지정](../../../docs/standard/base-types/composite-formatting.md)