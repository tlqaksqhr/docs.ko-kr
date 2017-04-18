---
title: "/errorreport | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ebe5646256926f68a1a900b91c25a1768505785
ms.lasthandoff: 03/13/2017

---
# <a name="errorreport"></a>/errorreport
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서 내부 컴파일러 오류를 보고하는 방식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>주의  
 이 옵션은 보고서에는 편리한 방법을 제공는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 을 내부 컴파일러 오류 (ICE)는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Microsoft 팀에서. 기본적으로 컴파일러는 Microsoft에 없는 정보를 보냅니다. 그러나 내부 컴파일러 오류를 발생을 수행 하면이 옵션을 사용 하면 Microsoft로 오류를 보고 하 합니다. 정보는 Microsoft 엔지니어가 원인을 파악 하는 데 도움이 되며의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
 보고서를 보내는 사용자의 능력 컴퓨터 및 사용자 정책 권한에 따라 달라 집니다.  
  
 다음 표에서 요약의 효과 `/errorreport` 옵션입니다.  
  
|옵션|동작|  
|---|---|  
|`prompt`|내부 컴파일러 오류가 발생 하는 경우는 대화 상자가 나타나는 컴파일러에서 수집한 정확한 데이터를 볼 수 있도록 합니다. 오류 보고에 대 한 중요 한 정보가 있는지 확인 수 있으며 Microsoft로 보낼지 여부를 결정을 내릴 수 있습니다. 를 보내려면 결정 하 고 컴퓨터 및 사용자 정책 설정에서 허용, 컴파일러는 데이터를 Microsoft로 보냅니다.|  
|`queue`|오류 보고서를 큐에 넣습니다. 관리자 권한으로 로그인 하는 경우에 기록 된 마지막 시간 이후 발생 한 모든 오류를 보고할 수 있습니다 (하지 묻습니다 보고서를 보내는 오류에 대 한 일에 한 번 이상). 이것이 기본 동작 때는 `/errorreport` 옵션을 지정 하지 않습니다.|  
|`send`|내부 컴파일러 오류가 발생 하 고 컴퓨터 및 사용자 정책 설정에서 허용, 컴파일러는 데이터를 Microsoft로 보냅니다.<br /><br /> 옵션 `/errorReport:send` Microsoft에 오류 정보를 자동으로 보내려고 시도 합니다. 이 옵션은 레지스트리에 따라 달라 집니다. 레지스트리에서 적절 한 값을 설정 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 2008 명령줄 도구에서 자동 오류 보고를 설정 하는 방법을](http://go.microsoft.com/fwlink/?LinkID=184695)합니다.|  
|`none`|내부 컴파일러 오류가 발생 하는 경우 그를 하지 수집 하거나 Microsoft로 전송 합니다.|  
  
 컴파일러는 일반적으로 일부 소스 코드를 포함 하는 오류 시 스택을 포함 하는 데이터를 보냅니다. 경우 `/errorreport` 와 함께 사용 되는 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 전체 소스 파일에 보내집니다.  
  
 이 옵션은 함께 사용할 가장는 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 보다 Microsoft 엔지니어가 오류를 쉽게 재현할 수 있습니다.  
  
> [!NOTE]
>  `/errorreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드를 컴파일하려고 시도 `T2.vb`, 한 컴파일러는 내부 컴파일러 오류가 발생 한 경우 Microsoft로 오류 보고서를 보낼 것인지 묻습니다.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
