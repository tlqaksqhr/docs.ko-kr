---
title: "/codepage (Visual Basic) | Microsoft 문서"
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
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
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
ms.openlocfilehash: 90dce6e34e52862807e2acdbf1850699316730d1
ms.lasthandoff: 03/13/2017

---
# <a name="codepage-visual-basic"></a>/codepage(Visual Basic)
컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`id`|필수 요소. 컴파일러에서 지정한 코드 페이지를 사용 하 여 `id` 소스 파일의 인코딩을 해석 합니다.|  
  
## <a name="remarks"></a>주의  
 특정 인코딩으로 저장 된 소스 코드를 컴파일하려면를 사용할 수 있습니다 `/codepage` 코드 페이지를 사용할지를 지정할 수 있습니다. `/codepage` 옵션 컴파일에 모든 소스 코드 파일에 적용 됩니다. 자세한 내용은 참조 [.NET Framework의 문자 인코딩을](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9)합니다.  
  
 `/codepage` 옵션에는 소스 코드 파일의 현재 ANSI 코드 페이지, 유니코드 또는 u t F-8을 사용 하 여 서명을 사용 하 여 저장 한 경우에 필요 하지 않습니다. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]사용자에서 다른 인코딩을 지정 하지 않으면 기본적으로 모든 소스 코드 파일의 현재 ANSI 코드 페이지와 저장 된 **인코딩** 대화 상자입니다. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]사용 하는 **인코딩** 대화 상자를 다른 코드 페이지와 함께 저장 하는 소스 코드 파일을 엽니다.  
  
> [!NOTE]
>  `/codepage` 옵션 내에서 사용할 수 없는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 개발 환경, 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
