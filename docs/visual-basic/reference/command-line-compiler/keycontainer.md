---
title: "/keycontainer | Microsoft 문서"
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
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 68fa09edce5c0c9af143197f9379d5a46afab52e
ms.lasthandoff: 03/13/2017

---
# <a name="keycontainer"></a>T:System.Reflection.AssemblyKeyNameAttribute
어셈블리에 강력한 이름을 지정하는 키 쌍의 키 컨테이너 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`container`|필수 요소. 키가 포함 된 파일의 컨테이너입니다. 파일 이름을 따옴표로 묶습니다 ("") 이름에 공백이 있는 경우.|  
  
## <a name="remarks"></a>주의  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 하 고 최종 어셈블리에 개인 키로 서명 하 여 공유할 수 있는 구성 요소를 만듭니다. 키 파일을 생성 하려면 다음을 입력 `sn -k``file` 명령줄에서. `-i` 옵션 컨테이너에 키 쌍을 설치 합니다. 자세한 내용은 [Sn.exe(강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)를 참조하세요.  
  
 로 컴파일할 경우 `/target:module`, 키 파일의 이름이 모듈에 저장 되 고 있는 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)합니다.  
  
 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyNameAttribute>) Microsoft MSIL (intermediate language) 모듈에 대 한 소스 코드에서.</xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 컴파일러에 암호화 정보를 전달할 수도 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)합니다. 사용 하 여 [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) 부분적으로 서명 된 어셈블리에 들어 있습니다.  
  
 참조 [Creating and using strong-named Assemblies](https://msdn.microsoft.com/library/xwb8f617) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
> [!NOTE]
>  `/keycontainer` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 소스 파일을 컴파일하 `Input.vb` 하 고 키 컨테이너를 지정 합니다.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
