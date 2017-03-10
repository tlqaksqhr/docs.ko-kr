---
title: "방법: 레거시 인코딩과 유니코드 간 변환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "변환[C#], 레거시-유니코드 인코딩"
  - "문자열[C#], 인코딩 간 변환"
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# 방법: 레거시 인코딩과 유니코드 간 변환(C# 프로그래밍 가이드)
C\#에서 메모리의 모든 문자열은 유니코드\(UTF\-16\)로 인코딩되므로  저장 장치의 데이터를 `string` 개체로 가져올 경우 데이터가 자동으로 UTF\-16으로 변환됩니다.  데이터에 0에서 127 사이의 ASCII 값만 들어 있는 경우에는 별도의 작업 없이 변환이 수행됩니다.  하지만 소스 텍스트에 확장 ASCII 바이트 값\(128에서 255 사이의 값\)이 들어 있는 경우 확장 문자는 기본적으로 현재 코드 페이지에 따라 해석됩니다.  소스 텍스트가 다른 코드 페이지에 따라 해석되도록 지정하려면 다음 예제에서 볼 수 있는 것처럼 <xref:System.Text.Encoding?displayProperty=fullName> 클래스를 사용해야 합니다.  
  
## 예제  
 다음 예제에서는 8비트 ASCII로 인코딩된 텍스트 파일의 소스 텍스트를 Windows 코드 페이지 737에 따라 해석하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#34)]  
  
## 참고 항목  
 [문자열](../../../csharp/programming-guide/strings/index.md)