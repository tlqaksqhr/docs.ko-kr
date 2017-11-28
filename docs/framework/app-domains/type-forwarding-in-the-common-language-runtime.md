---
title: "공용 언어 런타임의 형식 전달"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 18e580a67d5a983d61ab3c0b71cfc7d294468010
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>공용 언어 런타임의 형식 전달
형식 전달을 사용하면 원본 어셈블리를 사용하는 응용 프로그램을 다시 컴파일하지 않고도 형식을 다른 어셈블리로 이동할 수 있습니다.  
  
 예를 들어, 응용 프로그램에서 `Utility.dll`이라는 어셈블리의 `Example` 클래스를 사용할 경우 `Utility.dll` 개발자는 어셈블리를 리팩터링하고 해당 과정에서 `Example` 클래스를 다른 어셈블리로 이동할 수 있습니다. 이전 버전의 `Utility.dll`이 새 버전의 `Utility.dll`과 관련 어셈블리로 바뀐 경우 `Example` 클래스를 사용하는 응용 프로그램은 새 버전의 `Utility.dll`에서 `Example` 클래스를 찾을 수 없기 때문에 실패합니다.  
  
 `Utility.dll` 개발자는 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> 특성으로 `Example` 클래스에 대한 요청을 전달하여 이를 방지할 수 있습니다. 새 버전의 `Utility.dll`에 이 특성이 적용된 경우 `Example` 클래스에 대한 요청은 현재 해당 클래스가 들어 있는 어셈블리로 전달됩니다. 기존 응용 프로그램은 다시 컴파일하지 않고도 정상적으로 작동합니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서는 Visual Basic으로 작성된 어셈블리의 형식을 전달할 수 없습니다. 그러나 Visual Basic으로 작성된 응용 프로그램에서 전달된 형식을 사용할 수는 있습니다. 즉, 응용 프로그램에서 C# 또는 C++로 코딩된 어셈블리를 사용하며 해당 어셈블리의 형식이 다른 어셈블리로 전달된 경우 Visual Basic 응용 프로그램에서 전달된 형식을 사용할 수 있습니다.  
  
## <a name="forwarding-types"></a>형식 전달  
 다음 네 단계를 통해 형식을 전달할 수 있습니다.  
  
1.  형식의 소스 코드를 원본 어셈블리에서 대상 어셈블리로 이동합니다.  
  
2.  해당 형식이 있었던 어셈블리에서 이동된 형식에 대해 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>를 추가합니다. 다음 코드에서는 이동된 `Example` 형식의 특성을 보여 줍니다.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  해당 형식이 현재 들어 있는 어셈블리를 컴파일합니다.  
  
4.  해당 형식이 있었던 어셈블리를 현재 해당 형식이 들어 있는 어셈블리에 대한 참조를 사용하여 다시 컴파일합니다. 예를 들어, 명령줄에서 C# 파일을 컴파일할 경우 [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다. C++의 경우 소스 파일에서 [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) 지시문을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>  
 [형식 전달(C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)  
 [#using 지시문](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)
