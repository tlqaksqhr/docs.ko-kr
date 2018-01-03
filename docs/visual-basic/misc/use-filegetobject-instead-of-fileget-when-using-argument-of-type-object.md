---
title: "사용 &#39; FileGetObject &#39; 대신 &#39; Fileget 함수 &#39; 형식 &#39; 개체 &#39; 인수를 사용 하는 경우"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="2f871-102">사용 &#39; FileGetObject &#39; 대신 &#39; Fileget 함수 &#39; 형식 &#39; 개체 &#39; 인수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2f871-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="2f871-103">`FileGet` 메서드는 `Object`형식의 인수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2f871-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="2f871-104">모호성을 피하기 위해`FileGetObject` 대신 `FileGet` 를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f871-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="2f871-105">`My.Computer.Filesystem` 에서 제공하는 기능이 `FileGet` 또는 `FileGetObject`보다 사용하기 쉽고 성능이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="2f871-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f871-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="2f871-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="2f871-107">`FileGet` 을 `FileGetObject`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f871-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="2f871-108">`Object` 인수를 더 구체적인 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2f871-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f871-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f871-109">See Also</span></span>  
   
 [<span data-ttu-id="2f871-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="2f871-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
