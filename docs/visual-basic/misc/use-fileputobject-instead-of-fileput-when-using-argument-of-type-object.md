---
title: "사용 &#39; FilePutObject &#39; 대신 &#39; Fileput 함수 &#39; 형식 &#39; 개체 &#39; 인수를 사용 하는 경우"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cba4af206e2dbf767fdb883ec81229a67842c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>사용 &#39; FilePutObject &#39; 대신 &#39; Fileput 함수 &#39; 형식 &#39; 개체 &#39; 인수를 사용 하는 경우
`FilePut` 형식의 인수를 포함 하는 메서드 `Object`합니다. 모호성을 피하기 위해`FilePutObject` 대신 `FilePut` 를 사용해야 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   `FilePut` 을 `FilePutObject`로 바꿉니다.  
  
-   `Object` 인수를 더 구체적인 형식으로 캐스트합니다.  
  
-   `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [빌드에 없음: FilePutObject 함수](http://msdn.microsoft.com/en-us/a0f52a1c-5ecc-4945-b18c-03147af61d6b)  
 [My.Computer.FileSystem 개체](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)  
 [My.Computer.FileSystem.WriteAllBytes 메서드](http://msdn.microsoft.com/en-us/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)
