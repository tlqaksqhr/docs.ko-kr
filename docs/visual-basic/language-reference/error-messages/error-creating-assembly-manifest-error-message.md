---
title: "어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
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
ms.openlocfilehash: 35a912bbcab78178ce636afa550c244823da512c
ms.lasthandoff: 03/13/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다. 링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.  
  
 지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다. 어셈블리에 완전히 서명을 하려면 공개 키와 개인 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다. 어셈블리 서명을 연기을을 선택 해야는 **서명만 연기** 확인란을 선택 하 고 공개 키 정보에 대 한 정보가 포함 된 유효한 키 파일을 제공 합니다. 어셈블리 서명을 연기할 때 개인 키는 필요하지 않습니다. 자세한 내용은 참조 [하는 방법: 어셈블리 (Visual Studio)에 서명](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)합니다.  
  
 **오류 ID:** BC30140  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  따옴표로 묶인된 오류 메시지를 검사 하는 항목을 검토 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) AL1019 오류에 대 한 추가 설명과 권장  
  
2.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 어셈블리 서명(Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [프로젝트 디자이너, 서명 페이지](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer)   
 [Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex)   
 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
