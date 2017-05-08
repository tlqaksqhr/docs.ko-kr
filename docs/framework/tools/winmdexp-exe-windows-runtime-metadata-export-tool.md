---
title: "Winmdexp.exe(Windows Runtime 메타데이터 내보내기 도구) | Microsoft Docs"
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
  - "Windows Runtime 메타데이터 내보내기 도구"
  - "Winmdexp.exe"
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Winmdexp.exe(Windows Runtime 메타데이터 내보내기 도구)
[!INCLUDE[wrt](../../../includes/wrt-md.md)] Metadata Export Tool\(Winmdexp.exe\)은 .NET Framework 모듈을 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 메타데이터가 포함되는 파일로 변환합니다.  .NET Framework 어셈블리 및 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 메타데이터 파일이 같은 물리적 형식을 사용하지만 메타데이터 테이블의 내용에 차이가 있습니다. 즉, .NET Framework 어셈블리는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소로 자동으로 사용할 수 있습니다.  .NET Framework 모듈을 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소로 전환하는 프로세스를 *내보내기*라고 합니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 및 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]에서 결과 Windows 메타데이터\(.winmd\) 파일은 메타데이터와 구현이 모두 포함됩니다.  
  
 C\#에는 **Windows 스토어**에, [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 또는 [!INCLUDE[vs_dev11_ext](../../../includes/vs-dev11-ext-md.md)]에는 Visual Basic에 있는 **[!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소** 템플릿을 사용하면 컴파일러 대상은 .winmdobj 파일이고 이후 빌드 단계는 Winmdexp.exe를 호출하여 .winmdobj 파일을 .winmd 파일로 내보냅니다.  이러한 방법으로 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소를 빌드하는 것이 좋습니다.  Visual Studio가 제공하는 것보다 빌드 프로세스를 더 자세하게 제어하려면 Winmdexp.exe를 사용합니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다.  이 도구를 실행하려면 개발자 명령 프롬프트\(또는 Windows 7의 Visual Studio 명령 프롬프트\)를 사용합니다.  자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)을 참조하십시오.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## 구문  
  
```  
  
winmdexp [options] winmdmodule  
```  
  
#### 매개 변수  
  
|인수 또는 옵션|설명|  
|--------------|--------|  
|`winmdmodule`|내보낼 모듈\(.winmdobj\)을 지정합니다.  하나의 모듈만 허용됩니다.  이 모듈을 만들려면 `/target` 컴파일러 옵션을 `winmdobj` 대상과 함께 사용합니다.  MSDN 라이브러리의 [\/target:winmdobj\(Windows 런타임의 중간 파일 만들기\)](../Topic/-target:winmdobj%20\(C%23%20Compiler%20Options\).md) 또는 [\/target](../Topic/-target%20\(Visual%20Basic\).md)을 참조하십시오.|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Winmdexp.exe가 생성하는 출력 XML 문서 파일을 지정합니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 기본적으로 출력 파일이 XML 문서 파일과 같습니다.|  
|`/moduledoc:` `docfile`<br /><br /> `/md:` `docfile`|컴파일러가 `winmdmodule`로 생성한 XML 문서 파일의 이름을 지정합니다.|  
|`/modulepdb:` `symbolfile`<br /><br /> `/mp:` `symbolfile`|`winmdmodule`에 대한 기호를 포함하는 프로그램 데이터베이스\(PDB\) 파일의 이름을 지정합니다.|  
|`/nowarn:` `warning`|지정한 경고 번호를 표시하지 않습니다.  *warning*에 대해 오류 코드를 앞의 0 없이 숫자 부분만 제공합니다.|  
|`/out:` `file`<br /><br /> `/o:` `file`|출력 Windows 메타데이터\(.winmd\) 파일의 이름을 지정합니다.|  
|`/pdb:` `symbolfile`<br /><br /> `/p:` `symbolfile`|내보낸 Windows 메타데이터\(.winmd\) 파일의 기호를 포함하는 출력 프로그램 데이터베이스\(PDB\) 파일의 이름을 지정합니다.|  
|`/reference:` `winmd`<br /><br /> `/r:` `winmd`|내보내기 중 참조할 메타데이터 파일\(.winmd 또는 assembly\)을 지정합니다.  "\\Program Files \(x86\)\\Reference Assemblies\\Microsoft\\Framework\\.NETCore\\v4.5"의 참조 어셈블리\(32비트 컴퓨터의 경우 "\\Program Files\\..."\)를 사용하는 경우 System.Runtime.dll 및 mscorlib.dll 모두에 대한 참조를 포함합니다.|  
|`/utf8output`|출력 메시지가 UTF\-8 인코딩이 되도록 지정합니다.|  
|`/warnaserror+`|모든 경고를 오류로 처리하도록 지정합니다.|  
|**@** `responsefile`|옵션이 포함된 지시\(.rsp\) 파일이나 `winmdmodule`을 지정합니다.  `responsefile`의 각 줄은 하나의 인수 또는 옵션을 포함해야 합니다.|  
  
## 설명  
 Winmdexp.exe는 임의의 .NET Framework 어셈블리를 .winmd 파일로 변환할 수 없습니다.  `/target:winmdobj` 옵션으로 컴파일된 모듈이 필요하고 추가 제한 사항이 적용됩니다.  이러한 제한 사항 중 가장 중요한 사항은 어셈블리의 API 화면에 노출된 모든 형식이 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 형식이어야 하는 것입니다.  자세한 내용은 Windows 개발자 센터에 있는 [C\# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](http://go.microsoft.com/fwlink/p/?LinkID=238313) 문서의 "Windows 런타임 구성 요소에서 형식 선언" 단원을 참조하십시오.  
  
 C\# 또는 Visual Basic으로 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램 또는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소를 쓸 때, .NET Framework는 지원을 제공하여 [!INCLUDE[wrt](../../../includes/wrt-md.md)]을 사용한 프로그램을 더 자연스럽게 만듭니다.  이에 대해서는 [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) 문서에 자세히 설명되어 있습니다.  이 프로세스에서 몇 가지 자주 사용되는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 형식이 .NET Framework 형식으로 매핑됩니다.  Winmdexp.exe는 이 프로세스를 반대로 바꾸고 해당 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 형식을 사용하는 API 화면을 생성합니다.  예를 들어 <xref:System.Collections.Generic.IList%601> 인터페이스에서 구성된 형식은 [!INCLUDE[wrt](../../../includes/wrt-md.md)] [IVector\<T\>](http://go.microsoft.com/fwlink/p/?LinkId=251132) 인터페이스로 구성한 형식으로 매핑됩니다.  
  
## 참고 항목  
 [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)   
 [C\# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](http://go.microsoft.com/fwlink/p/?LinkID=238313)   
 [Winmdexp.exe 오류 메시지](../../../docs/framework/tools/winmdexp-exe-error-messages.md)   
 [Build, Deployment, and Configuration Tools \(.NET Framework\)](http://msdn.microsoft.com/ko-kr/b8c921be-6012-4181-b8d4-ab15813fc9a7)