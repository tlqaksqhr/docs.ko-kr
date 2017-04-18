---
title: "CorFlags.exe(CorFlags 변환 도구) | Microsoft Docs"
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
  - "CorFlags 변환 도구"
  - "CorFlags.exe"
  - "이식 가능한 실행 파일, CorFlags 섹션"
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# CorFlags.exe(CorFlags 변환 도구)
CorFlags 변환 도구를 사용하면 이식 가능한 실행 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다.  이 도구를 실행하려면 개발자 명령 프롬프트\(또는 Windows 7의 Visual Studio 명령 프롬프트\)를 사용합니다.  자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)을 참조하십시오.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## 구문  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### 매개 변수  
  
|필수적 매개 변수|설명|  
|---------------|--------|  
|`assembly`|CorFlags를 구성할 어셈블리의 이름입니다.|  
  
|옵션|설명|  
|--------|--------|  
|**\/32BIT\[REQ\]\+**|32BITREQUIRED 플래그를 설정합니다.|  
|**\/32BIT\[REQ\]\-**|32BITREQUIRED 플래그를 지웁니다.|  
|**\/32BITPREF\+**|32BITPREFERRED 플래그를 설정합니다.  응용 프로그램이 64비트 플랫폼에서 32비트 프로세스로 실행됩니다.  EXE 파일에만 이 플래그를 설정합니다.  DLL에 플래그가 설정되면 DLL은 64비트 프로세스 로드에 실패하고 <xref:System.BadImageFormatException> 예외가 throw됩니다.  이 플래그를 사용하여 EXE 파일은 64비트 프로세스에 로드할 수 있습니다.<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 새로 추가된 옵션입니다.|  
|**\/32BITPREF\-**|32BITPREFERRED 플래그를 지웁니다.<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 새로 추가된 옵션입니다.|  
|**\/?**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**\/Force**|어셈블리의 이름이 강력한 이름인 경우에도 업데이트합니다. **Important:**  강력한 이름의 어셈블리를 업데이트하면 코드를 실행하기 전에 다시 서명해야 합니다.|  
|**\/help**|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|**\/ILONLY\+**|ILONLY 플래그를 설정합니다.|  
|**\/ILONLY\-**|ILONLY 플래그를 지웁니다.|  
|**\/nologo**|Microsoft 시작 배너를 표시하지 않습니다.|  
|**\/RevertCLRHeader**|CLR 헤더 버전을 2.0으로 되돌립니다.|  
|**\/UpgradeCLRHeader**|CLR 헤더 버전을 2.5로 업그레이드합니다. **Note:**  기본적으로 어셈블리를 실행하려면 CLR 헤더 버전이 2.5 이상이어야 합니다.|  
  
## 설명  
 옵션을 지정하지 않으면 CorFlags 변환 도구에서 지정한 어셈블리에 대한 플래그를 표시합니다.  
  
## 참고 항목  
 [도구](../../../docs/framework/tools/index.md)   
 [64비트 응용 프로그램](../../../docs/framework/64-bit-apps.md)   
 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)