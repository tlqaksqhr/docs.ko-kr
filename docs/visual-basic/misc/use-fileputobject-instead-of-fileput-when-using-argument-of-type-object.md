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
ms.openlocfilehash: 5612c2bd4dc08f767643d2cd865a2ba1a8210c15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="e3ebb-102">사용 &#39; FilePutObject &#39; 대신 &#39; Fileput 함수 &#39; 형식 &#39; 개체 &#39; 인수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e3ebb-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="e3ebb-103">`FilePut` 형식의 인수를 포함 하는 메서드 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ebb-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="e3ebb-104">모호성을 피하기 위해`FilePutObject` 대신 `FilePut` 를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ebb-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3ebb-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e3ebb-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e3ebb-106">`FilePut` 을 `FilePutObject`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e3ebb-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="e3ebb-107">`Object` 인수를 더 구체적인 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ebb-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="e3ebb-108">`My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ebb-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ebb-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3ebb-109">See Also</span></span>  
   
 [<span data-ttu-id="e3ebb-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="e3ebb-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="e3ebb-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="e3ebb-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
