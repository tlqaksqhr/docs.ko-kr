---
title: 파일 모드가 잘못되었습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a><span data-ttu-id="34803-102">파일 모드가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34803-102">Bad file mode</span></span>
<span data-ttu-id="34803-103">파일 내용을 조작에 사용 된 파일을 연 모드에 적합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="34803-104">이 오류가 발생하는 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34803-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="34803-105">A `FilePutObject` 또는 `FileGetObject` 문을 순차적 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="34803-106">A `Print` 이외의 액세스 모드에 대 한 열린 파일을 지정 하는 문을 `Output` 또는 `Append`합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="34803-107">`Input` 이외의 액세스 모드에 대 한 열린 파일을 지정 하는 문`Input`</span><span class="sxs-lookup"><span data-stu-id="34803-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="34803-108">읽기 전용 파일에 쓰려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="34803-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="34803-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="34803-109">To correct this error</span></span>  
  
-   <span data-ttu-id="34803-110">확인 `FilePutObject` 및 `FileGetObject` 만 참조 하는 파일에 대 한 열기 `Random` 또는 `Binary` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="34803-111">확인 `Print` 중 하나에 대 한 열린 파일을 지정 `Output` 또는 `Append` 액세스 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="34803-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="34803-112">그렇지 않은 경우 파일에서 데이터를 배치 하는 다른 문을 사용 하거나 적절 한 모드에서 파일을 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="34803-113">확인 `Input` 에 대 한 열린 파일을 지정 `Input`합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="34803-114">그렇지 않은 경우 다른 문을 사용 하 여 데이터 파일에 배치 하거나 적절 한 모드에서 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="34803-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="34803-115">읽기 전용 파일에 작성 하는 경우 파일의 읽기/쓰기 상태를 변경 하거나 쓰려고 시도 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="34803-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="34803-116">`My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34803-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34803-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34803-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [<span data-ttu-id="34803-118">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="34803-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
