---
title: "어셈블리 서명 연기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리 서명 지연"
  - "어셈블리 서명"
  - "어셈블리[.NET Framework], 서명"
  - "강력한 이름의 어셈블리, 어셈블리 서명 연기"
  - "부분 어셈블리 서명"
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 어셈블리 서명 연기
특정 조직에서는 개발자의 경우에도 일상적으로 액세스하지 못하도록 철저히 보호하는 키 쌍이 존재할 수 있습니다.  대개 공개 키는 누구나 사용할 수 있지만, 개인 키는 소수의 몇몇 개인만 액세스할 수 있도록 제한됩니다.  강력한 이름의 어셈블리를 개발하는 경우, 이 강력한 이름의 대상 어셈블리를 참조하는 각 어셈블리에는 공개 키 토큰이 들어 있습니다. 이 공개 키 토큰은 대상 어셈블리에 강력한 이름을 지정합니다.  이렇게 하려면 개발 프로세스에서 공개 키를 사용할 수 있어야 합니다.  
  
 빌드 시에 지연 서명이나 부분 서명을 사용하면 강력한 이름 서명에 필요한 공간을 PE 파일에서 예약할 수 있습니다. 하지만 실제 서명은 어셈블리를 공급하기 바로 직전의 단계로 지연됩니다.  
  
 다음 단계는 어셈블리 서명을 연기하는 과정에 대해 설명합니다.  
  
1.  실제 서명을 수행할 조직으로부터 키 쌍의 공개 키 부분을 구합니다.  일반적으로 이 키는 .snk 파일 형식으로 되어 있으며 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 제공되는 [강력한 이름 도구\(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 만들 수 있습니다.  
  
2.  <xref:System.Reflection>의 두 사용자 지정 특성을 사용하여 어셈블리의 소스 코드에 주석을 답니다. 이 두 특성은 다음과 같습니다.  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute> 특성은 공개 키가 포함된 파일의 이름을 생성자에 매개 변수로 전달합니다.  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute> 특성은 **true**를 생성자에 매개 변수로 전달하여 서명 연기가 사용 중임을 나타냅니다.  예를 들면 다음과 같습니다.  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  컴파일러는 이 공개 키를 어셈블리 매니페스트에 삽입하고, 강력한 이름 서명에 필요한 공간을 PE 파일에서 예약합니다.  실제 공개 키는 어셈블리가 작성되는 중에 저장되어야 합니다. 그러면 이 어셈블리를 참조하는 다른 어셈블리에서 이 키를 가져가서 자체의 어셈블리 참조에 저장할 수 있습니다.  
  
4.  이 어셈블리에는 유효한 강력한 이름 서명이 없으므로, 서명 확인을 해제해야 합니다.  이 동작은 String Name 도구에서 **–Vr** 옵션을 사용하여 수행할 수 있습니다.  
  
     다음 예제는 `myAssembly.dll` 어셈블리에 대해 확인을 해제합니다.  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     Advanced RISC Machine \(ARM\) 마이크로프로세서와 같은 강력한 이름 도구를 실행할 수 없는 플랫폼 유효성을 해제 하기 위해 **–Vk** 옵션을 레지스트리 파일을 만들기 위해 사용합니다.  확인을 해제 하고 싶은 컴퓨터의 레지스트리에 레지스트리 파일을 가져옵니다.  다음 예제에서는 `myAssembly.dll`에 대한 레지스트리 파일을 만듭니다.  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     **–Vr** 또는 **–Vk** 옵션으로, 키 서명 테스트에 .snk 파일을 선택적으로 포함할 수도 있습니다.  
  
    > [!CAUTION]
    >  개발하는 동안에 **\-Vr** 또는 **–Vk** 옵션을 사용하십시오.  어셈블리를 확인 생략 목록에 추가하면 보안상 허점이 발생합니다.  악의적인 어셈블리가 확인 건너뛰기 목록에 추가된 어셈블리의 정규화된 어셈블리 이름\(어셈블리 이름, 버전, culture 및 공개 키 토큰\)을 사용하여 해당 어셈블리의 ID를 모방할 수 있습니다.  이렇게 되면 악의적인 어셈블리도 확인을 건너뛸 수 있습니다.  
  
    > [!NOTE]
    >  64비트 컴퓨터에서 Visual Studio를 사용한 배포 중에 서명 연기를 사용하고 **Any CPU**에 맞춰 어셈블리를 컴파일하는 경우 **\-Vr** 옵션을 두 번 적용해야 할 수도 있습니다. Visual Studio에서 **Any CPU**는 **플랫폼 대상** 빌드 속성의 값 중 하나이며 명령줄에서 컴파일하는 경우 기본값입니다. 응용 프로그램을 명령줄 또는 Windows 탐색기에서 실행하려면 64 비트 버전의 [Sn.exe\(강력한 이름 도구\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 를  **\-Vr** 옵션을 어셈블리에 적용하기 위해 사용합니다.  디자인 타임에 어셈블리를 Visual Studio로 로드하려는 경우\(예: 응용 프로그램의 다른 어셈블리에서 사용하는 구성 요소가 해당 어셈블리에 포함되어 있는 경우\) 32비트 버전의 강력한 이름 도구를 사용합니다.  JIT\(Just\-In\-Time\) 컴파일러는 어셈블리가 명령줄에서 실행되는 경우 어셈블리를 64비트 네이티브 코드로 컴파일하고, 어셈블리가 디자인 타임 환경으로 로드되는 경우에는 32비트 네이티브 코드로 컴파일하기 때문에 이 도구를 사용해야 합니다.  
  
5.  일반적으로 어셈블리를 공급하기 바로 직전에 이 어셈블리를 조직의 서명 기관에 제출하면, Strong Name 도구에서 **–R** 옵션을 사용하여 강력한 이름 서명을 실제로 수행합니다.  
  
     다음 예제는 `sgKey.snk` 키 쌍을 사용하여 강력한 이름으로 `myAssembly.dll` 어셈블리를 서명합니다.  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## 참고 항목  
 [어셈블리 만들기](../../../docs/framework/app-domains/create-assemblies.md)   
 [방법: 공개\/개인 키 쌍 만들기](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Sn.exe\(강력한 이름 도구\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)