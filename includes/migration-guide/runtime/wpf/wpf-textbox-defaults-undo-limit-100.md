### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="c2401-101">WPF TextBox 기본값이 100개의 제한을 실행 취소</span><span class="sxs-lookup"><span data-stu-id="c2401-101">WPF TextBox defaults to undo limit of 100</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c2401-102">설명</span><span class="sxs-lookup"><span data-stu-id="c2401-102">Details</span></span>|<span data-ttu-id="c2401-103">.NET Framework 4.5에서는 WPF TextBox에 대한 실행 취소 제한 기본값은 100(.NET Framework 4.0에서 무제한이던 것과 반대)</span><span class="sxs-lookup"><span data-stu-id="c2401-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>|
|<span data-ttu-id="c2401-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c2401-104">Suggestion</span></span>|<span data-ttu-id="c2401-105">100개의 실행 취소 제한이 너무 낮으면 제한을 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>로 명시적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2401-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>|
|<span data-ttu-id="c2401-106">범위</span><span class="sxs-lookup"><span data-stu-id="c2401-106">Scope</span></span>|<span data-ttu-id="c2401-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c2401-107">Edge</span></span>|
|<span data-ttu-id="c2401-108">버전</span><span class="sxs-lookup"><span data-stu-id="c2401-108">Version</span></span>|<span data-ttu-id="c2401-109">4.5</span><span class="sxs-lookup"><span data-stu-id="c2401-109">4.5</span></span>|
|<span data-ttu-id="c2401-110">형식</span><span class="sxs-lookup"><span data-stu-id="c2401-110">Type</span></span>|<span data-ttu-id="c2401-111">런타임</span><span class="sxs-lookup"><span data-stu-id="c2401-111">Runtime</span></span>|
|<span data-ttu-id="c2401-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c2401-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

