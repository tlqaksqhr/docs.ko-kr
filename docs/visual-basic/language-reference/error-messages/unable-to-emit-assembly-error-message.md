---
title: "어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dac4b133882c043f9c84e936bad2e36f35fc4c33
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다. 링커가 어셈블리 생성의 내보내기 단계에서 오류를 보고했습니다.  
  
 **오류 ID:** BC30145  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  따옴표로 묶인된 오류 메시지를 검사 하는 항목을 검토 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 추가 설명과 권장 사항을 대 한 합니다.  
  
2.  어셈블리 중 하나를 사용 하 여 수동으로 서명을 시도 [Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex) 또는 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)합니다.  
  
3.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
### <a name="to-sign-the-assembly-manually"></a>어셈블리에 수동으로 서명하려면  
  
1.  사용 된 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23) 공개/개인 키 쌍 파일을 만들려고 합니다.  
  
     이 파일의 확장명은 .snk입니다.  
  
2.  프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.  
  
3.  Windows에서 **시작** 메뉴에서 **프로그램**, 가리킨 **Microsoft Visual Studio 2008**, 가리킨 **Visual Studio Tools**를 클릭 하 고 **Visual Studio 2008 명령 프롬프트**합니다.  
  
4.  어셈블리 래퍼를 배치할 디렉터리로 이동합니다.  
  
5.  다음 코드를 입력합니다.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     입력할 수 있는 코드의 예는 다음과 같습니다.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     경로나 파일에 공백이 있으면 큰따옴표(")를 사용합니다.  
  
6.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]에서 방금 만든 파일에 대한 .NET 어셈블리 참조를 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex)   
 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)   
 [방법: 공개/개인 키 쌍 만들기](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)   
 [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
