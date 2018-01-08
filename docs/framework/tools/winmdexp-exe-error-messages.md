---
title: "Winmdexp.exe 오류 메시지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WME1095
- WME1110
- WME15
- WME1094
- WME1078
- WME1080
- WME1014
- WME1025
- WME1089
- WME1111
- WME1010
- WME1013
- WME1055
- WME1005
- WME1033
- WME1003
- WME1011
- WME1046
- WME0013
- WME1032
- WME1029
- WME1048
- WME1019
- WME1106
- WME0012
- WME1017
- WME1098
- WME1039
- WME20
- WME1006
- WME1088
- WME0004
- WME10
- WME12
- WME0015
- WME0017
- WME1026
- WME1045
- WME1002
- WME1051
- WME1107
- WME1100
- WME1072
- WME1090
- WME1105
- WME1022
- WME11
- WME17
- WME1063
- WME1041
- WME1057
- WME1037
- WME1007
- WME3
- WME1096
- WME0003
- WME0006
- WME1065
- WME1102
- WME1070
- WME1113
- WME1064
- WME1061
- WME1066
- WME1018
- WME1049
- WME1027
- WME1101
- WME1058
- WME0005
- WME1083
- WME1004
- WME1073
- WME1087
- WME1077
- WME19
- WME1086
- WME1085
- WME1040
- WME8
- WME1081
- WME1023
- WME4
- WME1050
- WME7
- WME1091
- WME14
- WME0007
- WME1024
- WME1012
- WME1036
- WME0010
- WME1104
- WME1035
- WME1021
- WME1075
- WME5
- WME13
- WME1074
- WME1028
- WME0014
- WME1030
- WME1008
- WME1052
- WME1079
- WME1054
- WME1093
- WME1042
- WME2
- WME1062
- WME6
- WME1001
- WME0011
- WME16
- WME0001
- WME1020
- WME1084
- WME1103
- WME1092
- WME1
- WME0002
- WME1112
- WME1016
- WME1060
- WME0008
- WME0016
- WME1097
- WME1034
- WME1108
- WME1082
- WME1099
- WME1069
- WME1031
- WME1009
- WME1068
- WME1067
- WME1059
- WME18
- WME1038
- WME0009
- WME1109
- WME1056
- WME1076
- WME1071
- WME1044
- WME1043
- WME1053
- WME1015
- WME1047
- WME9
helpviewer_keywords:
- Winmdexp.exe, error messages
- Windows Runtime Metadata Export Tool, error messages
- error messages, Winmdexp.exe
ms.assetid: 8271973c-deba-47a6-8e5e-04ce63f146ad
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22f556c87f676b86228fbb68f66206f3c39140cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="winmdexpexe-error-messages"></a><span data-ttu-id="1ac91-102">Winmdexp.exe 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="1ac91-102">Winmdexp.exe Error Messages</span></span>
<span data-ttu-id="1ac91-103">[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 **[!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소** 템플릿을 사용할 때 빌드 프로세스는 [Winmdexp.exe(Windows 런타임 메타데이터 내보내기 도구)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)를 호출하므로 Winmdexp.exe 오류 메시지가 **오류 목록**에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-103">The build process calls [Winmdexp.exe (Windows Runtime Metadata Export Tool)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md) when you use the **[!INCLUDE[wrt](../../../includes/wrt-md.md)] Component** template in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], so Winmdexp.exe error messages appear in the **Error List**.</span></span> <span data-ttu-id="1ac91-104">Winmdexp.exe는 `/target:winmdobj` 옵션으로 컴파일된 모듈에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-104">Winmdexp.exe operates on a module that is compiled with the `/target:winmdobj` option.</span></span> <span data-ttu-id="1ac91-105">컴파일된 모듈이 입력으로 필요하므로 컴파일에 성공하지 않으면 해당 오류 메시지가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-105">Because it requires a compiled module as input, its error messages don't appear unless compilation succeeds.</span></span>  
  
 <span data-ttu-id="1ac91-106">오류 메시지는 보고되는 오류 조건을 해결하는 데 필요한 모든 정보를 포함하도록 설계되었습니다. 그러나 몇 가지 문제에는 메시지에 표시되는 것보다 많은 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-106">The error messages are designed to contain all the information you need to address the error conditions they report.However, some problems require more information than will fit in the message.</span></span> <span data-ttu-id="1ac91-107">추가 정보는 Windows 개발자 센터의 [Windows 런타임 구성 요소 오류 조건 진단](http://go.microsoft.com/fwlink/p/?LinkId=251127)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-107">You can find additional information in [Diagnosing Windows Runtime component error conditions](http://go.microsoft.com/fwlink/p/?LinkId=251127) in the Windows Dev Center.</span></span>  
  
 <span data-ttu-id="1ac91-108">해당 문서에서 오류를 설명하지 않고 메시지에 문제 해결을 위한 정보가 충분히 포함되지 않은 경우 문서의 사용자 의견 링크를 사용하고 오류 메시지를 포함하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ac91-108">If your error is not discussed in that article, and you feel that the message doesn't contain sufficient information to address the issue, please use the feedback link in that article and include the error message.</span></span> <span data-ttu-id="1ac91-109">[Microsoft Connect 웹 사이트](http://go.microsoft.com/fwlink/p/?LinkId=251130)에서 버그를 보고할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-109">Alternatively, you can file a bug at the [Microsoft Connect website](http://go.microsoft.com/fwlink/p/?LinkId=251130).</span></span> <span data-ttu-id="1ac91-110">자세한 내용은 [Microsoft 포럼](http://go.microsoft.com/fwlink/p/?LinkId=251129)에서도 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ac91-110">You can also look for more information on the [Microsoft Forums](http://go.microsoft.com/fwlink/p/?LinkId=251129).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ac91-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ac91-111">See Also</span></span>  
 [<span data-ttu-id="1ac91-112">Winmdexp.exe(Windows 런타임 메타데이터 내보내기 도구)</span><span class="sxs-lookup"><span data-stu-id="1ac91-112">Winmdexp.exe (Windows Runtime Metadata Export Tool)</span></span>](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)  
 [<span data-ttu-id="1ac91-113">Windows 런타임 구성 요소 오류 조건 진단</span><span class="sxs-lookup"><span data-stu-id="1ac91-113">Diagnosing Windows Runtime component error conditions</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=251127)
