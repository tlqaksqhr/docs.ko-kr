---
title: "상호 운용성 개요(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 상호 운용성"
  - "C++ Interop"
  - "COM interop"
  - "상호 운용성, 상호 운용성 정보"
  - "플랫폼 호출"
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# 상호 운용성 개요(C# 프로그래밍 가이드)
이 항목에서는 C\# 관리 코드와 비관리 코드 간 상호 운용성을 제공하는 메서드에 대해 설명합니다.  
  
## 플랫폼 호출  
 *플랫폼 호출*은 DLL\(동적 연결 라이브러리\)에 구현된 관리되지 않는 함수\(예: Microsoft Win32 API의 함수\)를 관리 코드에서 호출할 수 있게 해 주는 서비스입니다.  플랫폼 호출 서비스는 내보낸 함수를 찾아 호출한 후 필요에 따라 해당 인수\(정수, 문자열, 배열, 구조 등\)를 상호 운용 경계에서 마샬링합니다.  
  
 자세한 내용은 [관리되지 않는 DLL 함수 사용](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md) 및 [방법: 플랫폼 호출을 사용하여 웨이브 파일 재생](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)을 참조하십시오.  
  
> [!NOTE]
>  CLR\([공용 언어 런타임](../Topic/Common%20Language%20Runtime%20\(CLR\).md)\)에서는 시스템 리소스에 대한 액세스를 관리합니다.  CLR 외부에 있는 비관리 코드를 호출하면 이러한 보안 메커니즘이 무시되므로 보안상 위험할 수 있습니다.  예를 들어, CLR 보안 메커니즘을 무시하고 비관리 코드에서 비관리 코드의 리소스를 직접 호출할 수 있습니다.  자세한 내용은 [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122)를 참조하십시오.  
  
## C\+\+ Interop  
 IJW\(It Just Works\)라고도 하는 C\+\+ interop 기능을 사용하여 네이티브 C\+\+ 클래스를 래핑할 수도 있습니다. 이렇게 래핑된 클래스는 C\# 또는 다른 .NET Framework 언어로 작성된 코드에서 사용할 수 있습니다.  이 작업을 수행하려면 네이티브 DLL 또는 COM 구성 요소를 래핑하는 C\+\+ 코드를 작성합니다.  다른 .NET Framework 언어와 달리 [!INCLUDE[vcprvc](../../../csharp/programming-guide/interop/includes/vcprvc-md.md)]에서는 상호 운용성이 지원되므로 관리 코드와 비관리 코드를 동일한 응용 프로그램뿐 아니라 동일한 파일에도 배치할 수 있습니다.  그런 다음 관리되는 어셈블리를 생성하기 위해 **\/clr** 컴파일러 스위치를 사용하여 C\+\+ 코드를 빌드합니다.  마지막으로 어셈블리에 대한 참조를 C\# 프로젝트에 추가한 후 다른 관리되는 클래스를 사용할 때와 같은 방법으로 래핑된 개체를 사용합니다.  
  
## C\#에 COM 구성 요소 노출  
 COM 구성 요소를 C\# 프로젝트에서 사용할 수 있습니다.  일반적인 단계는 다음과 같습니다.  
  
1.  사용할 COM 구성 요소를 찾아서 등록합니다.  regsvr32.exe를 사용하여 COM DLL을 등록하거나 등록 취소합니다.  
  
2.  COM 구성 요소 또는 형식 라이브러리에 대한 참조를 프로젝트에 추가합니다.  
  
     참조를 추가하면 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서는 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)를 사용하여 형식 라이브러리를 입력으로 받아서 .NET Framework interop 어셈블리를 출력합니다.  RCW\(런타임 호출 가능 래퍼\)라고도 하는 이 어셈블리에는 형식 라이브러리에 있는 COM 클래스 및 인터페이스를 래핑하는 관리되는 클래스 및 인터페이스가 들어 있습니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]는 생성된 어셈블리에 대한 참조를 프로젝트에 추가합니다.  
  
3.  RCW에 정의된 클래스의 인스턴스를 만듭니다.  이렇게 하면 COM 개체의 인스턴스가 만들어집니다.  
  
4.  다른 관리되는 개체를 사용할 때와 같은 방법으로 이 개체를 사용합니다.  이 개체가 가비지 수집에 의해 회수될 때 COM 개체의 인스턴스도 메모리에서 해제됩니다.  
  
 자세한 내용은 [.NET Framework에 COM 구성 요소 노출](../Topic/Exposing%20COM%20Components%20to%20the%20.NET%20Framework.md)를 참조하십시오.  
  
## COM에 C\# 노출  
 COM 클라이언트는 올바르게 노출된 C\# 형식을 사용할 수 있습니다.  C\# 형식을 노출하는 기본 단계는 다음과 같습니다.  
  
1.  interop 특성을 C\# 프로젝트에 추가합니다.  
  
     [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] 프로젝트 속성을 수정하여 어셈블리 COM을 표시할 수 있습니다.  자세한 내용은 [어셈블리 정보 대화 상자](/visual-studio/ide/reference/assembly-information-dialog-box)를 참조하십시오.  
  
2.  COM 형식 라이브러리를 생성하고 COM에 사용할 수 있도록 등록합니다.  
  
     COM interop에 대해 C\# 어셈블리를 자동으로 등록하도록 [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] 프로젝트 속성을 수정할 수 있습니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]는 [Regasm.exe\(어셈블리 등록 도구\)](../Topic/Regasm.exe%20\(Assembly%20Registration%20Tool\).md)를 사용하며 관리되는 어셈블리를 입력으로 받는 `/tlb` 명령줄 스위치를 사용하여 형식 라이브러리를 생성할 수 있습니다.  이 형식 라이브러리는 COM 클라이언트에서 관리되는 클래스를 만들 수 있도록 어셈블리의 `public` 형식을 설명하고 레지스트리 항목을 추가합니다.  
  
 자세한 내용은 [.NET Framework 구성 요소를 COM에 노출](../Topic/Exposing%20.NET%20Framework%20Components%20to%20COM.md) 및 [COM 클래스 예제](../../../csharp/programming-guide/interop/example-com-class.md)을 참조하십시오.  
  
## 참고 항목  
 [Interop 성능 향상](란?LinkId%20=%2099564)   
 [COM Interop 소개](란?LinkId%20=%20112406)   
 [관리 및 관리 되지 않는 코드 마샬링 사이의](란?LinkId%20=%20112398)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Advanced COM Interoperability](http://msdn.microsoft.com/ko-kr/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)