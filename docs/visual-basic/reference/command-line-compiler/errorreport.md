---
title: -errorreport
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dc321f7f927d68a9f270076640cbc6d31d2f6d5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="-errorreport"></a><span data-ttu-id="e362a-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="e362a-102">-errorreport</span></span>
<span data-ttu-id="e362a-103">Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e362a-104">구문</span><span class="sxs-lookup"><span data-stu-id="e362a-104">Syntax</span></span>  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="e362a-105">설명</span><span class="sxs-lookup"><span data-stu-id="e362a-105">Remarks</span></span>  
 <span data-ttu-id="e362a-106">이 옵션을 microsoft Visual Basic 팀 Visual Basic 내부 컴파일러 오류 (ICE)를 보고 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="e362a-107">기본적으로 컴파일러 정보가 Microsoft에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="e362a-108">그러나 내부 컴파일러 오류를 발생 수행 하면이 옵션 Microsoft로 오류를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="e362a-109">이 정보는 Microsoft 엔지니어가 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스에서 성능을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>  
  
 <span data-ttu-id="e362a-110">컴퓨터 및 사용자 정책 사용 권한에 사용자의 보고서를 보낼 수 있는 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="e362a-111">다음 표에서 요약의 효과 `-errorreport` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-111">The following table summarizes the effect of the `-errorreport` option.</span></span>  
  
|<span data-ttu-id="e362a-112">옵션</span><span class="sxs-lookup"><span data-stu-id="e362a-112">Option</span></span>|<span data-ttu-id="e362a-113">동작</span><span class="sxs-lookup"><span data-stu-id="e362a-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="e362a-114">내부 컴파일러 오류가 발생 하는 경우 컴파일러에서 수집한 정확한 데이터를 볼 수 있도록 대화 상자 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="e362a-115">모든 중요 한 정보가 오류 보고서에 없는 경우를 확인 하 고 Microsoft로 보낼지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="e362a-116">보내기,로 컴퓨터 및 사용자 정책 설정에서 허용 하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="e362a-117">오류 보고서를 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-117">Queues the error report.</span></span> <span data-ttu-id="e362a-118">관리자 권한으로 로그인 하는 경우에 기록 된 마지막 시간 이후 발생 한 모든 오류를 보고할 수 있습니다 (하면 메시지가 표시 되지 것입니다 3 일에 두 번 이상 실패에 대 한 보고서를 보내도록).</span><span class="sxs-lookup"><span data-stu-id="e362a-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="e362a-119">이것이 기본 동작 때는 `-errorreport` 옵션을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="e362a-120">내부 컴파일러 오류가 발생 하 고 컴퓨터 및 사용자 정책 설정에서 허용, 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="e362a-121">옵션 `-errorreport:send` Microsoft로 오류 정보를 자동으로 보내려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="e362a-122">이 옵션은 레지스트리에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-122">This option depends on the registry.</span></span> <span data-ttu-id="e362a-123">레지스트리에서 적절 한 값을 설정 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 2008 명령줄 도구에서 자동 오류 보고 설정 하는 방법](http://go.microsoft.com/fwlink/?LinkID=184695)합니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="e362a-124">내부 컴파일러 오류가 발생 하는 경우 그를 하지 수집 하거나 Microsoft로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="e362a-125">컴파일러는 일반적으로 일부 소스 코드를 포함 하는 오류 발생 시 스택을 포함 하는 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="e362a-126">경우 `-errorreport` 와 함께 사용 되는 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 전체 소스 파일에 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-126">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="e362a-127">이 옵션은 함께 사용할 가장는 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 더 많은 작업을 Microsoft 엔지니어가 오류를 쉽게 재현할 수 있기 때문에 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e362a-128">`-errorreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-128">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e362a-129">예제</span><span class="sxs-lookup"><span data-stu-id="e362a-129">Example</span></span>  
 <span data-ttu-id="e362a-130">다음 코드를 컴파일하려면 시도 `T2.vb`, 한 컴파일러에 내부 컴파일러 오류가 발생 하는 경우 Microsoft로 오류 보고서를 보낼 것인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="e362a-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e362a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e362a-131">See Also</span></span>  
 [<span data-ttu-id="e362a-132">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="e362a-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e362a-133">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="e362a-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="e362a-134">-bugreport</span><span class="sxs-lookup"><span data-stu-id="e362a-134">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
