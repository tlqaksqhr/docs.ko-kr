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
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="59ae8-102">Friend 어셈블리 참조 &lt;참조&gt; 사용할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="59ae8-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="59ae8-103">Friend 어셈블리 참조 \<참조 > 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59ae8-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="59ae8-104">강력한 이름의 서명된 어셈블리는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ae8-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="59ae8-105">에 전달 된 어셈블리 이름을 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에는 강력한 이름의 어셈블리를 식별 하지만 포함 되지 않습니다는 `PublicKey` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="59ae8-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="59ae8-106">**오류 ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="59ae8-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="59ae8-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="59ae8-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="59ae8-108">Friend 강력한 이름의 어셈블리에 대 한 공개 키를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ae8-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="59ae8-109">어셈블리 이름의 부분에 전달 된 공개 키를 포함 된 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자를 사용 하 여는 `PublicKey` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="59ae8-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ae8-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59ae8-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="59ae8-111">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="59ae8-111">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [<span data-ttu-id="59ae8-112">방법: 서명된 Friend 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="59ae8-112">How to: Create Signed Friend Assemblies</span></span>](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
