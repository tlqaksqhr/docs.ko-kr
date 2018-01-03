---
title: "Friend 어셈블리 참조 &lt;참조&gt; 사용할 수 없습니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab1c7c5cc7a7f4ad899df7722769238e05d96e6b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Friend 어셈블리 참조 &lt;참조&gt; 사용할 수 없습니다
Friend 어셈블리 참조 \<참조 > 사용할 수 없습니다. 강력한 이름의 서명된 어셈블리는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.  
  
 에 전달 된 어셈블리 이름을 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에는 강력한 이름의 어셈블리를 식별 하지만 포함 되지 않습니다는 `PublicKey` 특성입니다.  
  
 **오류 ID:** BC31535  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  Friend 강력한 이름의 어셈블리에 대 한 공개 키를 확인 합니다. 어셈블리 이름의 부분에 전달 된 공개 키를 포함 된 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자를 사용 하 여는 `PublicKey` 특성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.AssemblyName>  
 [Friend 어셈블리](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

