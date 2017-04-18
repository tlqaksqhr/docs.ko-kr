---
title: "동적 소스 코드 생성 및 컴파일 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 문서 개체 모델"
  - "CodeDOM"
  - "언어 독립적 소스 코드 모델링"
  - "언어, CodeDOM에 의한 여러 언어 지원"
  - "CodeDOM에 의해 지원되는 여러 언어"
  - "여러 언어로 된 소스 코드"
  - "System.CodeDom 네임스페이스"
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 동적 소스 코드 생성 및 컴파일
.NET Framework에는 프로그램 개발자가 레코딩할 코드를 나타내는 단일 모델을 기반으로 런타임에 소스 코드를 여러 프로그래밍 언어로 생성할 수 있도록 하는 CodeDOM\(코드 문서 개체 모델\)이라는 메커니즘이 포함되어 있습니다.  
  
 CodeDOM 요소는 소스 코드를 나타내기 위해 서로 연결되어 CodeDOM 그래프라고 하는 데이터 구조를 형성합니다. 이 그래프를 통해 일부 소스 코드 구조가 모델링됩니다.  
  
 `System.CodeDom` 네임스페이스는 특정 프로그래밍 언어에 관계없이 소스 코드의 논리적 구조를 나타낼 수 있는 형식을 정의합니다.  `System.CodeDom.Compiler` 네임스페이스는 CodeDOM 그래프를 바탕으로 소스 코드를 생성하고 지원되는 언어의 소스 코드 컴파일을 관리하기 위한 형식을 정의합니다.  컴파일러 공급업체나 개발업체에서는 지원 언어 집합을 확장할 수 있습니다.  
  
 프로그램에서 프로그램 모델용 소스 코드를 여러 언어 또는 정해지지 않은 대상 언어로 생성할 필요가 있을 때 언어 독립 모델링이 유용할 수 있습니다.  예를 들어, 해당 언어용 CodeDOM 지원을 사용할 수 있으면 CodeDOM을 언어 추출 인터페이스로 사용하여 정확한 프로그래밍 언어의 소스 코드를 생성하는 디자이너도 있습니다.  
  
 .NET Framework에는 [C\#](frlrfMicrosoftCSharpCSharpCodeProviderClassTopic), [JScript](frlrfMicrosoftJScriptJScriptCodeProviderClassTopic) 및 [Visual Basic](frlrfMicrosoftVisualBasicVBCodeProviderClassTopic)용 코드 생성기와 코드 컴파일러가 포함되어 있습니다.  
  
## 단원 내용  
 [CodeDOM 사용](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 CodeDOM을 사용하여 간단한 개체 그래프를 빌드하는 방법을 보여 주고 CodeDOM의 일반적인 기능에 대해 설명합니다.  
  
 [소스 코드 생성 및 CodeDOM 그래프에서 프로그램 컴파일](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 소스 코드를 생성한 후, 생성된 코드를 `System.CodeDom.Compiler` 네임스페이스에 정의된 클래스를 사용하여 외부 컴파일러로 컴파일하는 방법을 설명합니다.  
  
 [방법: CodeDOM을 사용하여 XML 문서 파일 만들기](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 CodeDOM을 사용하여 XML 문서 주석이 있는 코드를 생성하고 생성된 코드를 컴파일하여 XML 문서를 출력하는 방법을 설명합니다.  
  
 [방법: CodeDOM을 사용하여 클래스 만들기](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 CodeDOM을 사용하여 필드, 속성, 메서드, 생성자 및 진입점이 들어 있는 클래스를 생성하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.CodeDom>  
 공용 런타임을 목적으로 하는 프로그래밍 언어에서 코드 요소를 나타내는 요소를 정의합니다.  
  
 <xref:System.CodeDom.Compiler>  
 런타임에 코드를 생성 및 편집하는 인터페이스를 정의합니다.  
  
## 관련 단원  
 [CodeDOM Quick Reference](http://msdn.microsoft.com/ko-kr/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 개발자가 소스 코드 요소를 나타내는 CodeDOM 요소를 빨리 찾을 수 있는 방법을 제공합니다.