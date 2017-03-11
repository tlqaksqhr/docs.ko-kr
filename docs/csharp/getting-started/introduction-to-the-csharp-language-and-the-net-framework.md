---
title: "Introduction to the C# Language and the .NET Framework | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# language, about C# language"
  - "Visual C#, about"
ms.assetid: 0a2dff4e-cd84-42ff-8141-e89889b24081
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# Introduction to the C# Language and the .NET Framework
C\#은 개발자가 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]에서 실행되는 다양한 범위의 안전하고 견고한 응용 프로그램을 만들 수 있는 환경을 제공하는 세련되고 형식 안전적인 개체 지향 언어입니다.  C\#을 사용하여 Windows 클라이언트 응용 프로그램, XML Web Services, 분산 구성 요소, 클라이언트\/서버 응용 프로그램, 데이터베이스 응용 프로그램 등을 만들 수 있습니다.  Visual C\#은 고급 코드 편집기, 편리한 사용자 인터페이스 디자이너 및 통합된 디버거를 비롯하여 C\# 언어 및 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] 기반의 응용 프로그램을 손쉽게 개발하는 데 사용할 수 있는 다양한 도구를 제공합니다.  
  
> [!NOTE]
>  [!INCLUDE[csprcs](../../csharp/includes/csprcs-md.md)] 설명서는 사용자가 기본적인 프로그래밍 개념을 이해하고 있는 것으로 가정합니다.  프로그래밍에 처음 입문하는 사용자는 웹에서 [!INCLUDE[csprcsxpr](../../csharp/getting-started/includes/csprcsxpr-md.md)]에 대해 탐색해 보십시오.  또한 C\#에 대해 설명하는 교재와 웹 자료를 활용하여 실질적인 프로그래밍 기술을 익힐 수도 있습니다.  
  
## C\# 언어  
 C\# 구문은 표현력이 뛰어나면서도 단순하고 배우기 쉽습니다.  C\#의 중괄호 구문은 C, C\+\+ 또는 Java에 익숙한 사용자라면 누구나 쉽게 알아볼 수 있으며,  이러한 언어에 익숙한 개발자는 일반적으로 매우 짧은 기간 내에 C\#을 사용하여 생산성을 발휘할 수 있을 것입니다.  C\# 구문은 C\+\+의 여러 복잡한 구문을 단순화하는 한편 Java에서 제공하지 않는 nullable 값 형식, 열거형, 대리자, 람다 식 및 직접 메모리 액세스와 같은 강력한 기능을 제공합니다.  C\#에서는 향상된 형식 안전성과 성능을 제공하는 제네릭 메서드와 형식 및 컬렉션 클래스의 구현자가 클라이언트 코드에서 쉽게 사용할 수 있는 사용자 정의 반복 동작을 정의할 수 있게 하는 반복기를 지원합니다.  [!INCLUDE[vbteclinqext](../../csharp/getting-started/includes/vbteclinqext-md.md)] 식을 통해 강력한 형식의 쿼리가 고급 언어 구문이 됩니다.  
  
 C\#은 개체 지향 언어로서 캡슐화, 상속 및 다형성과 같은 개념을 지원합니다.  응용 프로그램의 진입접인 `Main` 메서드를 비롯한 모든 메서드와 모든 변수는 클래스 정의 안에 캡슐화됩니다.  클래스가 직접 상속할 수 있는 부모 클래스는 하나뿐이지만 구현할 수 있는 인터페이스의 개수에는 제한이 없습니다.  실수로 재정의하는 것을 피하기 위해, 부모 클래스에 있는 가상 메서드를 재정의하는 메서드에는 `override` 키워드를 사용해야 합니다.  C\#에서 구조체는 간단한 클래스와 같으며, 인터페이스를 구현할 수 있지만 상속을 지원하지 않는 스택에 할당되는 형식입니다.  
  
 이러한 기본적인 개체 지향 원리 이외에도 C\#은 다음과 같은 여러 가지 혁신적인 언어 구문을 통해 소프트웨어 구성 요소를 쉽게 개발할 수 있는 환경을 제공합니다.  
  
-   형식 안전적인 이벤트 알림을 가능하게 하는 캡슐화된 메서드 시그니처인 *대리자*  
  
-   전용 멤버 변수에 대한 접근자 역할을 하는 속성  
  
-   런타임에 형식에 대한 선언적 메타데이터를 제공하는 특성  
  
-   인라인 XML 문서 주석  
  
-   다양한 데이터 소스에서 기본 제공 쿼리 기능을 제공하는 [!INCLUDE[vbteclinqext](../../csharp/getting-started/includes/vbteclinqext-md.md)]  
  
 COM 개체 또는 네이티브 Win32 DLL과 같은 기타 Windows 소프트웨어와 상호 작용해야 하는 경우 "Interop"라는 프로세스를 통해 C\#에서 이를 수행할 수 있습니다. Interop를 통해 C\# 프로그램은 네이티브 C\+\+ 응용 프로그램에서 가능한 거의 모든 작업을 수행할 수 있습니다.  C\#은 직접 메모리 액세스가 절대적으로 중요한 경우를 위한 "안전하지 않은" 코드의 개념과 포인터도 지원합니다.  
  
 C\#의 개발 절차는 C와 C\+\+에 비해 간단하며 Java보다 유연합니다.  별도의 헤더 파일이 없으며 메서드와 형식을 특정 순서대로 선언해야 할 필요가 없습니다.  C\# 소스 파일에서 정의할 수 있는 클래스, 구조체, 인터페이스 및 이벤트의 개수에는 제한이 없습니다.  
  
 다음은 C\#에 대한 추가 자료입니다.  
  
-   C\# 언어에 대해 전반적으로 소개한 내용을 보려면 [C\# 언어 사양](../../csharp/language-reference/language-specification.md)의 1장을 참조하십시오.  
  
-   C\# 언어의 구체적인 특징에 대한 자세한 내용은 [C\# 참조](../../csharp/language-reference/index.md)를 참조하십시오.  
  
-   [!INCLUDE[vbteclinq](../../csharp/includes/vbteclinq-md.md)]에 대한 자세한 내용은 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)를 참조하십시오.  
  
-   Visual C\# 팀에서 제공하는 최신 기사와 리소스를 보려면 [Visual C\# Developer Center](http://go.microsoft.com/fwlink/?LinkId=47811)를 참조하십시오.  
  
## .NET Framework 플랫폼 아키텍처  
 C\# 프로그램은 CLR\(공용 언어 런타임\)이라는 가상 실행 시스템 및 통합된 클래스 라이브러리 집합이 포함된 Windows 필수 구성 요소인 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]에서 실행됩니다.  CLR은 다양한 언어와 라이브러리가 매끄럽게 함께 작동하는 실행 및 개발 환경을 구축하는 데 기준이 되는 국제 표준 CLI\(공용 언어 인프라\)를 Microsoft에서 상업용으로 구현한 것입니다.  
  
 C\#으로 작성된 소스 코드는 CLI 사양을 따르는 IL\(Intermediate Language\)로 컴파일됩니다.  IL 코드와 리소스\(예: 비트맵 및 문자열\)는 일반적인 확장명이 .exe 또는 .dll인 어셈블리라는 실행 파일로 디스크에 저장됩니다.  어셈블리에는 어셈블리의 형식, 버전, 문화권 및 보안 요구 사항에 대한 정보를 제공하는 매니페스트가 포함되어 있습니다.  
  
 C\# 프로그램을 실행하면 어셈블리가 CLR로 로드되고 CLR은 매니페스트에 포함된 정보를 기반으로 다양한 작업을 수행합니다.  그런 다음 보안 요구 사항이 충족되면 CLR은 JIT\(Just In Time\) 컴파일을 수행하여 IL 코드를 네이티브 기계어 명령으로 변환합니다.  CLR은 또한 자동 가비지 수집, 예외 처리 및 리소스 관리와 관련된 기타 서비스를 제공합니다.  CLR을 통해 실행되는 코드를 "관리 코드"라고도 하며, 이는 특정 시스템을 대상으로 하는 네이티브 기계어로 컴파일되는 "비관리 코드"와 대조적인 의미입니다.  다음 다이어그램은 C\# 소스 코드 파일, .NET Framework 클래스 라이브러리, 어셈블리 및 CLR의 컴파일 타임 및 런타임 관계를 보여 줍니다.  
  
 ![C&#35; 소스 코드에서 컴퓨터 실행으로](../../csharp/getting-started/media/netarchitecture.png "NETarchitecture")  
  
 언어 상호 운용성은 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]의 핵심적인 특징입니다.  C\# 컴파일러에서 생성하는 IL 코드는 CTS\(공용 형식 사양\)를 따르므로 C\#에서 생성하는 IL 코드는 Visual Basic, Visual C\+\+ 또는 20개 이상의 기타 CTS 규격 언어의 .NET 버전에서 생성하는 코드와 상호 작용할 수 있습니다.  단일 어셈블리에 다양한 .NET 언어로 작성된 여러 개의 모듈이 포함될 수 있고, 각 형식에서는 동일한 언어로 작성된 것처럼 다른 형식을 참조할 수 있습니다.  
  
 런타임 서비스 이외에도 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]에는 파일 입력 및 출력에서부터 문자열 조작, XML 구문 분석 및 Windows Forms 컨트롤에 이르는 유용한 기능을 광범위하게 제공하는 4,000개 이상의 클래스가 네임스페이스로 구조화되어 구성된 방대한 라이브러리가 포함되어 있습니다.  일반적인 C\# 응용 프로그램에서는 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스 라이브러리를 다방면으로 사용하여 일반적인 단순 기능을 처리합니다.  
  
 .NET Framework에 대한 자세한 내용은 [Overview of the Microsoft .NET Framework](http://msdn.microsoft.com/ko-kr/d05daf50-00fe-45c7-8383-06fe41697355)를 참조하십시오.  
  
## 중요 설명서 장  
 [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)의 [C\# Language Fundamentals](http://go.microsoft.com/fwlink/?LinkId=195416)  
  
 [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)의 [C\# and .NET Programming](http://go.microsoft.com/fwlink/?LinkId=195413)  
  
 [Visual C\# 2010 시작](http://go.microsoft.com/fwlink/?LinkId=221214)의 [C\# 소개](http://go.microsoft.com/fwlink/?LinkId=221226)  
  
 [Learning C\# 3.0: Master the fundamentals of C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)의 [Visual Studio 2008 and C\# Express 2008](http://go.microsoft.com/fwlink/?LinkId=195414)  
  
## 참고 항목  
 [C\#](../../csharp/csharp.md)   
 [Visual C\# 및 Visual Basic 시작](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic)