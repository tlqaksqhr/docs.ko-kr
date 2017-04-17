---
title: "동적 언어 런타임 개요 | Microsoft Docs"
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
  - "DLR"
  - "동적 언어 런타임"
  - "IronPython"
  - "IronRuby"
ms.assetid: f769a271-8aff-4bea-bfab-6160217ce23d
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# 동적 언어 런타임 개요
DLR\(*동적 언어 런타임*\)은 동적 언어에 대한 일련의 서비스를 CLR\(공용 언어 런타임\)에 추가하는 런타임 환경입니다.  DLR을 사용하면 .NET Framework에서 실행할 동적 언어를 더 쉽게 개발할 수 있고 정적 형식의 언어에 동적 기능을 더 쉽게 추가할 수 있습니다.  
  
 동적 언어는 런타임에 개체의 형식을 식별할 수 있는 반면, C\# 및 Visual Basic\(`Option Explicit On`을 사용하는 경우\) 같은 정적 형식의 언어에서는 디자인 타임에 개체 형식을 지정해야 합니다.  동적 언어의 예로는 Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra, Groovy 등이 있습니다.  
  
 개발자는 대부분의 동적 언어에서 다음과 같은 이점을 얻을 수 있습니다.  
  
-   신속한 피드백 루프\(REPL, Read\-Evaluate\-Print Loop\)를 사용할 수 있습니다.  따라서 여러 개의 문을 입력하고 해당 문을 즉시 실행하여 결과를 확인할 수 있습니다.  
  
-   하향식 개발 및 좀 더 일반적인 상향식 개발을 모두 지원합니다.  예를 들어 하향식 접근 방식을 사용하는 경우 아직 구현되지 않은 함수를 호출한 다음 필요할 때 내부 구현을 추가할 수 있습니다.  
  
-   코드 전체에서 정적 형식 선언을 변경할 필요가 없으므로 리팩터링과 코드 수정을 더 간편하게 해결할 수 있습니다.  
  
 동적 언어는 매우 뛰어난 스크립트 언어입니다.  사용자는 동적 언어를 사용하여 만든 응용 프로그램을 새 명령과 기능으로 쉽게 확장할 수 있습니다.  동적 언어는 웹 사이트와 테스트 도구를 만들고, 서버 팜을 유지 관리하고, 다양한 유틸리티를 개발하고, 데이터 변환을 수행하는 데도 자주 사용됩니다.  
  
 DLR의 목적은 동적 언어 시스템을 .NET Framework에서 실행할 수 있도록 하고 .NET 상호 운용성을 확보하는 데 있습니다.  DLR을 통해 Visual Studio 2010의 C\# 및 Visual Basic으로 동적 개체를 가져와 이들 언어에서 동적 동작을 지원하고 이들 언어와 동적 언어 사이에 상호 운용이 가능하게 할 수 있습니다.  
  
 DLR을 사용하면 동적 작업을 지원하는 라이브러리를 만드는 데도 도움이 됩니다.  예를 들어 XML 또는 JSON\(JavaScript Object Notation\) 개체를 사용하는 라이브러리가 있는 경우 DLR을 사용하는 언어에 해당 개체를 동적 개체로 표시할 수 있습니다.  이렇게 하면 라이브러리 사용자가 개체를 사용하여 작업하고 개체 멤버에 액세스하기 위한 코드를 더 간단하고 더 자연스러운 구문으로 작성할 수 있습니다.  
  
 예를 들어 C\#의 XML에서 카운터 값을 증가시키는 데 다음과 같은 코드를 사용할 수 있습니다.  
  
 `Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);`  
  
 DLR을 사용하면 동일한 작업에 다음과 같은 코드를 대신 사용할 수 있습니다.  
  
 `scriptobj.Count += 1;`  
  
 CLR과 마찬가지로 DLR은 .NET Framework의 일부이며 .NET Framework 및 Visual Studio 설치 패키지와 함께 제공됩니다.  오픈 소스 버전의 DLR은 또한 [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) 웹 사이트에서 다운로드 받을 수 있습니다.  
  
> [!NOTE]
>  오픈 소스 버전의 DLR에는 Visual Studio 및 .NET Framework와 함께 제공되는 DLR의 기능이 모두 포함됩니다.  또한 오픈 소스 버전의 DLR은 언어 구현자도 추가로 지원합니다.  자세한 내용은 [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028)웹 사이트의 설명서를 참조하십시오.  
  
 DLR을 사용하여 개발된 언어의 예로 다음과 같은 것이 있습니다.  
  
-   IronPython.  [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141040) 웹 사이트에서 오픈 소스 소프트웨어가 사용될 수 있습니다.  
  
-   IronRuby.  [RubyForge](http://go.microsoft.com/fwlink/?LinkId=141044) 웹 사이트에서 오픈 소스 소프트웨어가 사용될 수 있습니다.  
  
## DLR의 주요 이점  
 DLR을 사용하면 다음과 같은 이점이 있습니다.  
  
### 동적 언어를 .NET Framework로 간단히 이식할 수 있습니다.  
 DLR을 사용하면 언어를 구현하기 위해 일반적으로 직접 만들어야 했던 어휘 분석기, 파서, 의미 체계 분석기, 코드 생성기 및 기타 도구를 만들지 않아도 됩니다.  DLR을 사용하려면 언어 수준 코드를 트리 형태의 구조로 나타내는 *식 트리*, 런타임 도우미 루틴 및 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스를 구현하는 선택적인 동적 개체를 언어에서 생성해야 합니다.  DLR과 .NET Framework에서는 코드 분석 및 코드 생성 작업 중 많은 부분이 자동으로 처리됩니다.  따라서 언어를 구현할 때 언어 고유의 기능에 좀 더 집중할 수 있습니다.  
  
### 정적 형식의 언어에서 동적 기능을 사용할 수 있습니다.  
 C\# 및 Visual Basic 같은 기존의 .NET Framework 언어에서 동적 개체를 만들고 이를 정적 형식의 개체와 함께 사용할 수 있습니다.  예를 들어 C\# 및 Visual Basic에서 HTML, DOM\(문서 개체 모델\) 및 .NET 리플렉션에 동적 개체를 사용할 수 있습니다.  
  
### 추후 제공될 DLR 및 .NET Framework의 이점을 활용할 수 있습니다.  
 DLR을 사용하여 구현한 언어에서는 앞으로 있을 DLR과 .NET Framework의 향상된 기능을 활용할 수 있습니다.  예를 들어 가비지 수집기의 성능이 향상되거나 어셈블리 로드 시간이 단축된 새 버전의 .NET Framework가 발표되면 DLR을 사용하여 구현한 언어에서도 그 즉시 동일한 혜택을 누릴 수 있습니다.  DLR에서 컴파일 성능 향상 등과 같은 최적화가 추가로 이루어지면 DLR을 사용하여 구현되는 모든 언어의 성능도 함께 향상됩니다.  
  
### 라이브러리와 개체를 공유할 수 있습니다.  
 한 언어에서 구현되는 개체와 라이브러리를 다른 언어에 사용할 수 있습니다.  또한 DLR을 사용하면 정적 형식의 언어와 동적 언어 사이에 상호 운용성도 확보할 수 있습니다.  예를 들어 C\#에서 동적 언어로 작성된 라이브러리를 사용하는 동적 개체를 선언할 수 있습니다.  마찬가지로 동적 언어에서는 .NET Framework의 라이브러리를 사용할 수 있습니다.  
  
### 동적 디스패치 및 호출 속도를 향상시킬 수 있습니다.  
 DLR에서는 고급 다형성 캐싱을 지원하므로 동적 작업을 빠르게 실행할 수 있습니다.  DLR에서는 개체가 사용되는 작업을 필수 런타임 구현에 바인딩하는 규칙을 만든 다음 이러한 규칙을 캐싱하므로 개체의 동일한 형식에 대해 동일한 코드를 연속으로 실행하는 동안 바인딩을 계산하고 처리하느라 리소스를 낭비하지 않습니다.  
  
## DLR 아키텍처  
 다음 그림에서는 동적 언어 런타임의 아키텍처를 보여 줍니다.  
  
 ![동적 언어 아키텍처 개요](../../../docs/framework/reflection-and-codedom/media/dlr-archoverview.png "DLR\_ArchOverview")  
DLR 아키텍처  
  
 DLR은 더 나은 동적 언어 지원을 위해 CLR에 일련의 서비스를 추가합니다.  이렇게 추가되는 서비스는 다음과 같습니다.  
  
-   식 트리.  DLR에서는 언어 의미 체계를 나타내는 데 식 트리를 사용합니다.  이를 위해 DLR에서는 LINQ 식 트리를 확장하여 제어 흐름, 할당 및 기타 언어 모델링 노드를 추가했습니다.  자세한 내용은 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
-   호출 사이트 캐싱.  *동적 호출 사이트*는 동적 개체에 대해 `a + b` 또는 `a.b()` 같은 작업을 수행하는 코드의 위치입니다.  DLR에서는 대개 이러한 개체의 형식을 나타내는 `a` 및 `b`의 특징과 작업 관련 정보를 캐싱합니다.  이전에 그와 같은 작업을 수행한 적이 있으면 DLR에서 캐시를 대상으로 모든 필요한 정보를 검색하여 디스패치 속도를 향상시킵니다.  
  
-   동적 개체 상호 운용성.  DLR에서는 동적 개체 및 작업을 나타내는 일련의 클래스와 인터페이스를 제공합니다. 언어를 구현하거나 동적 라이브러리를 작성할 때 이렇게 제공되는 클래스와 인터페이스를 사용할 수 있습니다.  여기에 해당하는 클래스와 인터페이스로는 <xref:System.Dynamic.IDynamicMetaObjectProvider>, <xref:System.Dynamic.DynamicMetaObject>, <xref:System.Dynamic.DynamicObject> 및 <xref:System.Dynamic.ExpandoObject>가 있습니다.  
  
 DLR에서는 호출 사이트의 바인더를 사용하여 .NET Framework와 통신할 뿐만 아니라 Silverlight 및 COM을 비롯한 기타 인프라 및 서비스와도 통신합니다.  바인더는 언어의 의미 체계를 캡슐화하고 식 트리를 사용하여 호출 사이트에서 작업을 수행하는 방법을 지정합니다.  그 결과로 DLR을 사용하는 동적 언어와 정적 형식의 언어에서 라이브러리를 공유할 수 있고 DLR이 지원하는 모든 기술에 액세스할 수 있습니다.  
  
## DLR 문서  
 오픈 소스 버전의 DLR을 사용하여 언어에 동적 동작을 추가하는 방법이나 .NET Framework에 동적 언어를 사용할 수 있도록 하는 방법에 대한 자세한 내용은 [CodePlex](http://go.microsoft.com/fwlink/?LinkId=141028) 웹 사이트에서 제공하는 문서를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Dynamic.ExpandoObject>   
 <xref:System.Dynamic.DynamicObject>   
 [공용 언어 런타임](../../../docs/standard/clr.md)   
 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: 동적 개체 만들기 및 사용](../Topic/Walkthrough:%20Creating%20and%20Using%20Dynamic%20Objects%20\(C%23%20and%20Visual%20Basic\).md)