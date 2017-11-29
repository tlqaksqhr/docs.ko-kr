---
title: "경로 파일 액세스 오류입니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a><span data-ttu-id="62710-102">경로/파일 액세스 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="62710-102">Path/File access error</span></span>
<span data-ttu-id="62710-103">파일 액세스 또는 디스크 액세스 작업 중 운영 체제의 경로 파일 이름 간의 연결을 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="62710-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="62710-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="62710-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="62710-105">파일 사양의 형식이 올바로 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62710-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="62710-106">정규화 된 (절대) 또는 상대 파일 이름에 포함할 수 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="62710-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="62710-107">(다른 드라이브에 경로가) 하는 경우 드라이브 이름으로 정규화 된 경로 시작 하 고 파일에 루트에서 명시적인 경로 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="62710-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="62710-108">정규화 되지 않은 모든 경로 현재 드라이브와 디렉터리에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="62710-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="62710-109">기존 읽기 전용 파일을 대체 하는 파일을 저장 하려고 시도 하지 않았습니다 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62710-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="62710-110">이 경우 대상 파일의 읽기 전용 특성을 변경 또는 다른 이름으로 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="62710-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="62710-111">순차적 읽기 전용 파일을 열려고 하지 확인 `Output` 또는 `Append` 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="62710-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="62710-112">이 경우에서 파일을 엽니다 `Input` 모드 또는 파일의 읽기 전용 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="62710-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="62710-113">변경 하려고 하지 않았습니다 있는지 확인 한 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터베이스 또는 문서 내에서 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="62710-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62710-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62710-114">See Also</span></span>  
 [<span data-ttu-id="62710-115">오류 형식</span><span class="sxs-lookup"><span data-stu-id="62710-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
