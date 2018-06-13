---
title: 사용 하 여 &#39;FilePutObject&#39; 대신 &#39;FilePut&#39; 형식의 인수를 사용 하는 경우 &#39;개체&#39;
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 529352d98c175981c20861205ce04c8a2ebcdca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641130"
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>사용 하 여 &#39;FilePutObject&#39; 대신 &#39;FilePut&#39; 형식의 인수를 사용 하는 경우 &#39;개체&#39;
`FilePut` 형식의 인수를 포함 하는 메서드 `Object`합니다. 모호성을 피하기 위해`FilePutObject` 대신 `FilePut` 를 사용해야 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   `FilePut` 을 `FilePutObject`로 바꿉니다.  
  
-   `Object` 인수를 더 구체적인 형식으로 캐스트합니다.  
  
-   `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
