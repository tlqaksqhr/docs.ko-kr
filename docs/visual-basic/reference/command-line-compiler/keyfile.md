---
title: "/keyfile | Microsoft 문서"
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
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
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
ms.openlocfilehash: c36eac96ac6302db0b567e8249af726c807c2c6c
ms.lasthandoff: 03/13/2017

---
# <a name="keyfile"></a>T:System.Reflection.AssemblyKeyFileAttribute
어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>인수  
 `file`  
 필수 요소. 키가 포함 된 파일입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").  
  
## <a name="remarks"></a>설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 한 다음 개인 키와 함께 최종 어셈블리에 서명 합니다. 키 파일을 생성 하려면 다음을 입력 `sn -k file` 명령줄에서. 자세한 내용은 [Sn.exe(강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)를 참조하세요.  
  
 로 컴파일할 경우 `/target:module`, 키 파일의 이름이 모듈에 저장 되 고 있는 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)합니다.  
  
 컴파일러에 암호화 정보를 전달할 수도 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)합니다. 사용 하 여 [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) 부분적으로 서명 된 어셈블리에 들어 있습니다.  
  
 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyFileAttribute>) Microsoft 중간 언어 모듈에 대 한 소스 코드에서.</xref:System.Reflection.AssemblyKeyFileAttribute>  
  
 두 경우 `/keyfile` 및 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 지정 됩니다 (명령줄 옵션이 나 사용자 지정 특성)을 동일한 컴파일에서 컴파일러는 키 컨테이너를 먼저 시도 합니다. 시도 성공 하면 키 컨테이너의 정보로는 어셈블리가 서명 됩니다. 컴파일러는 키 컨테이너를 찾지 못하면 지정 된 파일 시도 `/keyfile`합니다. 이 작업이 성공 하면, 어셈블리 키 파일의 정보로 서명 되 고 키 정보는 키 컨테이너에 설치 됩니다 (비슷합니다 `sn -i`)는 다음에 컴파일할 키 컨테이너를 사용할 수 있도록 합니다.  
  
 키 파일에 공개 키만 포함 될 참고 합니다.  
  
 참조 [Creating and using strong-named Assemblies](https://msdn.microsoft.com/library/xwb8f617) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
> [!NOTE]
>  `/keyfile` 옵션 내에서 사용할 수 없는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 개발 환경, 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 소스 파일을 컴파일하 `Input.vb` 하 고 키 파일을 지정 합니다.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
