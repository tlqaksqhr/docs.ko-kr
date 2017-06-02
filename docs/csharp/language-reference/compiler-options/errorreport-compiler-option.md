---
title: "-errorreport(C# 컴파일러 옵션) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /errorreport
dev_langs:
- CSharp
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34e7e3b8c6a9f645ec1b359095c2d289afd1370a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="errorreport-c-compiler-options"></a>/errorreport(C# 컴파일러 옵션)
이 옵션은 C# 내부 컴파일러 오류를 Microsoft에 보고하는 편리한 방법을 제공합니다.  
  
> [!NOTE]
>  Windows Vista 및 Windows Server 2008에서 Visual Studio에 대한 오류 보고 설정은 WER(Windows 오류 보고)을 통한 설정을 재정의하지 않습니다. 항상 WER 설정이 Visual Studio 오류 보고 설정보다 우선합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a>인수  
 **none**  
 내부 컴파일러 오류에 대한 보고서를 수집하거나 Microsoft로 보내지 않습니다.  
  
 **prompt**  
 내부 컴파일러 오류가 발생하면 보고서를 보낼지 묻는 메시지를 표시합니다. **prompt**는 개발 환경에서 응용 프로그램을 컴파일할 때 기본값입니다.  
  
 **queue**  
 오류 보고서를 큐에 넣습니다. 관리자 자격 증명으로 로그온하면 마지막으로 로그온한 시간 이후에 발생한 모든 오류를 보고할 수 있습니다. 3일에 두 번 이상 오류 보고서를 보내라는 메시지가 표시되지는 않습니다. **queue**는 명령줄에서 응용 프로그램을 컴파일할 때의 기본값입니다.  
  
 **send**  
 내부 컴파일러 오류 보고서를 Microsoft에 자동으로 보냅니다. 이 옵션을 사용하려면 먼저 Microsoft 데이터 수집 정책에 동의해야 합니다. 처음으로 컴퓨터에서 **/errorreport:send**를 지정하면 Microsoft 데이터 수집 정책 웹 사이트로 안내하는 컴파일러 메시지가 나타납니다.  
  
 이 옵션은 레지스트리 설정에 따라 달라집니다. 레지스트리에서 적절한 값을 설정하는 방법에 대한 자세한 내용은 MSDN 웹 사이트에서 [Visual Studio 2008 명령줄 도구에서 자동 오류 보고를 설정하는 방법](http://go.microsoft.com/fwlink/?LinkID=184695)을 참조하세요.  
  
## <a name="remarks"></a>주의  
 내부 컴파일러 오류(ICE)는 컴파일러에서 소스 코드 파일을 처리할 수 없을 때 발생합니다. ICE가 발생하면 컴파일러에서 출력 파일 또는 코드를 수정하는 데 사용할 수 있는 유용한 진단을 생성하지 않습니다.  
  
 이전 릴리스에서는 ICE를 수신하는 경우 Microsoft 기술 지원 서비스에 문의하여 문제를 보고하도록 했습니다. **/errorreport**를 사용하여 Visual C# 팀에 ICE 정보를 제공할 수 있습니다. 오류 보고서는 향후 컴파일러 릴리스를 개선하는 데 도움이 됩니다.  
  
 사용자가 보고서를 보내는 능력은 컴퓨터 및 사용자 정책 권한에 따라 달라집니다.  
  
 오류 디버거에 대한 자세한 내용은 [Windows용 Dr. Watson(Drwtsn32.exe) 도구에 대한 설명](http://go.microsoft.com/fwlink/?LinkId=147286)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성** 페이지를 엽니다. 자세한 내용은 [프로젝트 디자이너, 빌드 페이지(C#)](https://docs.microsoft.com/visualstudio/ide/reference/build-page-project-designer-csharp)를 참조하세요.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **내부 컴파일러 오류 보고** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)
