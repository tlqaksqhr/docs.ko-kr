---
title: Windows Forms의 파일 및 데이터 액세스 추가 보안
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61e4893ac32d2013b090a748078ec1e3a84ea3ac
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="3727d-102">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="3727d-102">More Secure File and Data Access in Windows Forms</span></span>
<span data-ttu-id="3727d-103">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 리소스 및 데이터 보호를 위해 권한을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-103">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses permissions to help protect resources and data.</span></span> <span data-ttu-id="3727d-104">응용 프로그램이 데이터를 일거나 쓸 수 있는 위치는 응용 프로그램에 부여된 권한에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="3727d-105">응용 프로그램이 부분 신뢰 환경에서 실행되는 경우 데이터에 대한 액세스 권한이 없거나 데이터에 액세스하는 방법을 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="3727d-106">보안 제한이 발생할 경우 다음 두가지 옵션이 있습니다. 권한을 어설션(응용 프로그램에 부여되었다고 가정)하거나 부분 신뢰에서 작동하도록 작성된 기능 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="3727d-107">다음 섹션에서는 부분 신뢰 환경에서 실행 중인 응용 프로그램에서 파일, 데이터베이스 및 레지스트리 액세스 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3727d-108">기본적으로 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 배포를 생성하는 도구는 이러한 배포의 기본값을 실행되는 컴퓨터에서 완전 신뢰 요청으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-108">By default, tools that generate [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="3727d-109">부분 신뢰로 실행의 추가 보안 이점을 사용하려는 경우 이 기본값을 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 도구 중 하나(Mage.exe 또는 MageUI.exe)로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or one of the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="3727d-110">응용 프로그램에 대 한 적절 한 신뢰 수준을 확인 하는 방법 및 Windows Forms 보안에 대 한 자세한 내용은 참조 [의 보안 Windows Forms 개요](../../../docs/framework/winforms/security-in-windows-forms-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="3727d-111">파일 액세스</span><span class="sxs-lookup"><span data-stu-id="3727d-111">File Access</span></span>  
 <span data-ttu-id="3727d-112"><xref:System.Security.Permissions.FileIOPermission> 클래스는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 파일 및 폴더 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="3727d-113">기본적으로 보안 시스템은 로컬 인트라넷 및 인터넷 영역과 같은 부분 신뢰 환경에 <xref:System.Security.Permissions.FileIOPermission>을 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="3727d-114">그러나 응용 프로그램의 디자인을 수정하거나 다른 메서드를 사용하여 파일에 액세스하는 경우 파일 액세스가 필요한 응용 프로그램이 여전히 이러한 환경에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="3727d-115">기본적으로 로컬 인트라넷 영역에는 동일한 사이트 액세스 및 동일한 디렉터리 액세스를 포함하고, 원본 사이트에 다시 연결하고, 설치 디렉터리에서 읽을 수 있는 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="3727d-116">기본적으로 인터넷 영역에는 원본 사이트에 다시 연결할 수 있는 권한만 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="3727d-117">사용자 지정 파일</span><span class="sxs-lookup"><span data-stu-id="3727d-117">User-Specified Files</span></span>  
 <span data-ttu-id="3727d-118">파일 액세스 권한 없음을 처리하는 한 가지 방법은 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog> 클래스를 통해 특정 파일 정보를 제공하라는 메시지를 사용자에게 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="3727d-119">이 사용자 상호 작용은 응용 프로그램이 악의적으로 개인 파일을 로드하거나 중요한 파일을 덮어쓸 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="3727d-120"><xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 및 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드는 사용자가 지정한 파일에 대한 파일 스트림을 열어 읽기 및 쓰기 파일 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="3727d-121">메서드는 파일 경로가 표시되지 않도록 하여 사용자 파일 보호를 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3727d-122">이러한 권한은 응용 프로그램이 인터넷 영역 또는 인트라넷 영역에 있는지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="3727d-123">인터넷 영역 응용 프로그램은 <xref:System.Windows.Forms.OpenFileDialog>만 사용할 수 있는 반면 인트라넷 응용 프로그램은 무제한 파일 대화 상자 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="3727d-124"><xref:System.Security.Permissions.FileDialogPermission> 클래스는 응용 프로그램에서 사용할 수 있는 파일 형식 대화 상자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="3727d-125">다음 표에서는 각 <xref:System.Windows.Forms.FileDialog> 클래스를 사용하는 데 필요한 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="3727d-126">클래스</span><span class="sxs-lookup"><span data-stu-id="3727d-126">Class</span></span>|<span data-ttu-id="3727d-127">필요한 액세스 값</span><span class="sxs-lookup"><span data-stu-id="3727d-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
>  <span data-ttu-id="3727d-128"><xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드가 실제로 호출될 때까지 특정 권한이 요청되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="3727d-129">파일 대화 상자를 표시할 수 있는 권한은 응용 프로그램에 <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스의 모든 멤버에 대한 모든 권한을 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="3727d-130">각 메서드를 호출하는 데 필요한 정확한 권한은 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 클래스 라이브러리 설명서에서 해당 메서드에 대한 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3727d-130">For the exact permissions that are required to call each method, see the reference topic for that method in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library documentation.</span></span>  
  
 <span data-ttu-id="3727d-131">다음 코드 예제에서는 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용하여 사용자 지정 파일을 <xref:System.Windows.Forms.RichTextBox> 컨트롤에 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="3727d-132">예제를 사용하려면 <xref:System.Security.Permissions.FileDialogPermission> 및 연결된 <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> 열거형 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="3727d-133">예제에서는 <xref:System.Security.SecurityException>을 처리하여 저장 기능을 사용하지 않도록 설정할지 여부를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="3727d-134">이 예제를 사용하려면 <xref:System.Windows.Forms.Form>에 `ButtonOpen`이라는 <xref:System.Windows.Forms.Button> 컨트롤과 `RtfBoxMain`이라는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3727d-135">저장 기능에 대한 프로그래밍 논리는 예제에 표시되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click   
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try   
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()   
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try   
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then   
                ' The application does not have unrestricted permission   
                ' to the file so the save feature will be disabled.  
                saveAllowed = False   
            Else   
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)   
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)   
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())   
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try   
        {  
            editingFileName = openFileDialog1.FileName;  
        }   
        catch (Exception ex)   
        {  
            if (ex is System.Security.SecurityException)   
            {  
                // The application does not have unrestricted permission   
                // to the file so the save feature will be disabled.  
                saveAllowed = false;   
            }   
            else   
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="3727d-136">Visual C#, 이벤트 처리기를 사용 하는 코드를 추가 하는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="3727d-137">이전 예제의 코드를 사용하여 다음 코드에서는 이벤트 처리기 `this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="3727d-138">기타 파일</span><span class="sxs-lookup"><span data-stu-id="3727d-138">Other Files</span></span>  
 <span data-ttu-id="3727d-139">응용 프로그램 설정을 유지해야 하는 경우와 같이 사용자가 지정하지 않는 파일을 읽거나 써야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="3727d-140">로컬 인트라넷 및 인터넷 영역에서는 로컬 파일에 데이터를 저장할 수 있는 권한이 응용 프로그램에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="3727d-141">그러나 응용 프로그램은 격리된 저장소에 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="3727d-142">격리된 저장소는 데이터가 저장된 실제 디렉터리 위치를 포함하는 하나 이상의 격리된 저장소 파일(저장소라고 함)이 포함된 추상 데이터 컴파트먼트(특정 저장소 위치가 아님)입니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="3727d-143"><xref:System.Security.Permissions.FileIOPermission>과 같은 파일 액세스 권한은 필요하지 않습니다. 대신, <xref:System.Security.Permissions.IsolatedStoragePermission> 클래스는 격리된 저장소에 대한 권한을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="3727d-144">기본적으로 로컬 인트라넷 및 인터넷 영역에서 실행 중인 응용 프로그램은 격리된 저장소를 사용하여 데이터를 저장할 수 있습니다. 그러나 디스크 할당량과 같은 설정이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="3727d-145">격리 된 저장소에 대 한 자세한 내용은 참조 [격리 된 저장소](../../../docs/standard/io/isolated-storage.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-145">For more information about isolated storage, see [Isolated Storage](../../../docs/standard/io/isolated-storage.md).</span></span>  
  
 <span data-ttu-id="3727d-146">다음 예제에서는 격리된 저장소를 사용하여 저장소에 있는 파일에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="3727d-147">예제를 사용하려면 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 및 <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> 열거형 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="3727d-148">예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 특정 속성 값을 읽고 격리된 저장소의 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="3727d-149">`Read` 함수는 응용 프로그램이 시작된 후에 호출되고 `Write` 함수는 응용 프로그램이 종료되기 전에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="3727d-150">예제를 실행 하려면는 `Read` 및 `Write` 함수의 멤버로 존재는 <xref:System.Windows.Forms.Form> 를 포함 하는 <xref:System.Windows.Forms.Button> 라는 컨트롤 `MainButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values   
' for the button if the options file does not exist.  
Public Sub Read()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try   
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _   
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _   
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _   
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()   
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _   
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try   
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try   
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _   
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _   
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _   
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values   
// for the button if the options file does not exist.  
public void Read()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =   
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try   
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =   
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =   
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {   
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }   
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()   
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =   
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try   
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)   
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)   
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try   
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new   
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,   
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {   
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="3727d-151">데이터베이스 액세스</span><span class="sxs-lookup"><span data-stu-id="3727d-151">Database Access</span></span>  
 <span data-ttu-id="3727d-152">데이터베이스에 액세스하는 데 필요한 권한은 데이터베이스 공급자에 따라 다릅니다. 그러나 적절한 권한으로 실행 중인 응용 프로그램만 데이터 연결을 통해 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="3727d-153">데이터베이스에 액세스 하는 데 필요한 사용 권한에 대 한 자세한 내용은 참조 [코드 액세스 보안 및 ADO.NET](../../../docs/framework/data/adonet/code-access-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](../../../docs/framework/data/adonet/code-access-security.md).</span></span>  
  
 <span data-ttu-id="3727d-154">부분 신뢰로 응용 프로그램을 실행하려 하므로 데이터베이스에 직접 액세스할 수 없는 경우 데이터에 액세스하는 대체 방법으로 웹 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="3727d-155">웹 서비스는 네트워크를 통해 프로그래밍 방식으로 액세스할 수 있는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="3727d-156">웹 서비스를 통해 응용 프로그램은 코드 그룹 영역 간에 데이터를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="3727d-157">기본적으로 로컬 인트라넷 및 인터넷 영역의 응용 프로그램에는 동일한 서버에서 호스트된 웹 서비스를 호출할 수 있게 해주는 원본 사이트 액세스 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="3727d-158">자세한 내용은 참조 [ASP.NET AJAX의 웹 서비스](http://msdn.microsoft.com/library/8290e543-7eff-47a4-aace-681f3c07229b) 또는 [Windows Communication Foundation](http://msdn.microsoft.com/library/ms735119.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-158">For more information see [Web Services in ASP.NET AJAX](http://msdn.microsoft.com/library/8290e543-7eff-47a4-aace-681f3c07229b) or [Windows Communication Foundation](http://msdn.microsoft.com/library/ms735119.aspx).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="3727d-159">레지스트리 액세스</span><span class="sxs-lookup"><span data-stu-id="3727d-159">Registry Access</span></span>  
 <span data-ttu-id="3727d-160"><xref:System.Security.Permissions.RegistryPermission> 클래스는 운영 체제 레지스트리에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="3727d-161">기본적으로 로컬에서 실행 중인 응용 프로그램만 레지스트리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="3727d-162"><xref:System.Security.Permissions.RegistryPermission>은 레지스트리 액세스 시도 권한만 응용 프로그램에 부여합니다. 운영 체제가 여전히 레지스트리에 대한 보안을 적용하므로 액세스가 성공한다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="3727d-163">부분 신뢰에서는 레지스트리에 액세스할 수 없으므로 다른 데이터 저장 방법을 찾아야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="3727d-164">응용 프로그램 설정을 저장하는 경우 레지스트리 대신 격리된 저장소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="3727d-165">격리된 저장소를 사용하여 다른 응용 프로그램 관련 파일을 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="3727d-166">또한 기본적으로 응용 프로그램에 원본 사이트 액세스 권한이 부여되므로 서버 또는 원본 사이트에 대한 전역 응용 프로그램 정보를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3727d-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3727d-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3727d-167">See Also</span></span>  
 [<span data-ttu-id="3727d-168">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="3727d-168">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 [<span data-ttu-id="3727d-169">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3727d-169">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="3727d-170">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="3727d-170">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="3727d-171">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="3727d-171">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)  
 [<span data-ttu-id="3727d-172">Mage.exe(매니페스트 생성 및 편집 도구)</span><span class="sxs-lookup"><span data-stu-id="3727d-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 [<span data-ttu-id="3727d-173">MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)</span><span class="sxs-lookup"><span data-stu-id="3727d-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
