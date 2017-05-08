---
title: "COM에 어셈블리 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, 어셈블리 등록"
  - "비관리 코드와의 상호 운용, 어셈블리 등록"
  - "어셈블리 등록"
  - "어셈블리 등록 취소"
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# COM에 어셈블리 등록
[어셈블리 등록 도구\(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)라는 명령줄 도구를 실행하여 COM에서 사용할 어셈블리를 등록하거나 등록을 취소할 수 있습니다.  Regasm.exe COM 클라이언트에서.NET Framework 클래스를 투명 하 게 사용할 수 있도록 클래스에 대 한 정보를 시스템 레지스트리에 추가 합니다.  <xref:System.Runtime.InteropServices.RegistrationServices> 클래스에서는 여기에 해당하는 기능을 제공합니다.  
  
 관리되는 구성 요소는 Windows 레지스트리에 등록되어야 COM 클라이언트에서 활성화될 수 있습니다.  다음 표에서는 Regasm.exe가 일반적으로 Windows 레지스트리에 추가하는 키를 보여 줍니다.  000000은 실제 GUID 값을 나타냅니다.  
  
|GUID|설명|레지스트리 키|  
|----------|--------|-------------|  
|CLSID|클래스 식별자|HKEY\_CLASSES\_ROOT\\CLSID\\{000…000}|  
|IID|인터페이스 식별자|HKEY\_CLASSES\_ROOT\\Interface\\{000…000}|  
|LIBID|라이브러리 식별자|HKEY\_CLASSES\_ROOT\\TypeLib\\{000…000}|  
|ProgID|프로그래밍 식별자|HKEY\_CLASSES\_ROOT\\000…000|  
  
 HKCR\\CLSID\\{0000…0000} 키를 사용하면 기본값은 클래스의 ProgID로 설정되며 새로운 이름의 두 값, 즉 Class와 Assembly가 추가됩니다.  런타임에서는 레지스트리의 어셈블리 값을 읽은 다음, 해당 값을 런타임 어셈블리 확인기에 전달하며  어셈블리 확인기에서는 어셈블리의 이름 및 버전 번호와 같은 정보를 사용하여 어셈블리의 위치 찾기를 시도합니다.  어셈블리 확인기가 어셈블리를 찾기 위해서는 어셈블리가 다음 위치 중 한 곳에 있어야 합니다.  
  
-   전역 어셈블리 캐시\(강력한 이름의 어셈블리여야 함\).  
  
-   응용 프로그램 디렉터리.  응용 프로그램 경로에서 로드된 어셈블리는 해당 응용 프로그램에서만 액세스할 수 있습니다.  
  
-   **\/codebase** 옵션으로 Regasm.exe에 지정된 파일 경로  
  
 Regasm.exe는 HKCR\\CLSID\\{0000…0000} 키에 InProcServer32 키도 만듭니다.  이 키의 기본값은 공용 언어 런타임\(Mscoree.dll\)을 초기화하는 DLL의 이름으로 설정되어 있습니다.  
  
## 레지스트리 항목 검사  
 COM interop에서는 모든 .NET Framework 클래스의 인스턴스를 만들 수 있도록 표준 클래스 팩터리를 구현합니다.  클라이언트에서는 다른 COM 구성 요소에서와 마찬가지로, 관리되는 DLL에 **DllGetClassObject**를 호출하여 클래스 팩터리를 가져오고 개체를 만들 수 있습니다.  
  
 에 `InprocServer32` 하위 키를 mscoree.dll 공용 언어 런타임에서 관리 되는 개체를 만듭니다를 나타내기 위해 일반적인 COM 형식 라이브러리 대신 나타납니다.  
  
## 참고 항목  
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [방법: COM에서 .NET 형식 참조](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/ko-kr/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/ko-kr/fb63564c-c1b9-4655-a094-a235625882ce)