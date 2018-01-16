<span data-ttu-id="92b4e-101">Das Installieren eines Pakets kann auf drei Arten erfolgen:</span><span class="sxs-lookup"><span data-stu-id="92b4e-101">Installing a package happens in three ways:</span></span>

| <span data-ttu-id="92b4e-102">Methode</span><span class="sxs-lookup"><span data-stu-id="92b4e-102">Method</span></span> | <span data-ttu-id="92b4e-103">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92b4e-103">Description</span></span> | <span data-ttu-id="92b4e-104">Verweis</span><span class="sxs-lookup"><span data-stu-id="92b4e-104">Reference</span></span> |
| --- | --- | --- |
| <span data-ttu-id="92b4e-105">nuget.exe-Befehlszeilenschnittstelle: `nuget install <package_name>`</span><span class="sxs-lookup"><span data-stu-id="92b4e-105">nuget.exe CLI: `nuget install <package_name>`</span></span> | <span data-ttu-id="92b4e-106">Das anhand von \<package_name\> (Paket_Name) identifizierte Paket wird heruntergeladen und dessen Inhalt im aktuellen Verzeichnis in einen Ordner entpackt.</span><span class="sxs-lookup"><span data-stu-id="92b4e-106">Downloads the package identified by \<package_name\> and expands its contents into a folder in the current directory.</span></span> <span data-ttu-id="92b4e-107">Wenn keine Pakete angegeben werden, werden alle Pakete installiert, die in der Datei `packages.config` des Projekts aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="92b4e-107">If no packages are specified, installs all packages listed in the project's `packages.config` file.</span></span> <span data-ttu-id="92b4e-108">An den Projektdateien werden keine Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="92b4e-108">No changes are made to any project files.</span></span> <span data-ttu-id="92b4e-109">Abhängigkeiten werden auch heruntergeladen und entpackt.</span><span class="sxs-lookup"><span data-stu-id="92b4e-109">Dependencies are also downloaded and expanded.</span></span> | [<span data-ttu-id="92b4e-110">Referenz für die Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="92b4e-110">CLI reference</span></span>](../tools/nuget-exe-CLI-Reference.md) |
| <span data-ttu-id="92b4e-111">Paket-Manager-Konsole (Visual Studio): `Install-Package <package_name>`</span><span class="sxs-lookup"><span data-stu-id="92b4e-111">Package Manager Console (Visual Studio): `Install-Package <package_name>`</span></span> | <span data-ttu-id="92b4e-112">Das Paket wird in das aktuelle Projekt heruntergeladen und installiert, dann wird die Projektdatei aktualisiert, um das Paket als Abhängigkeit aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="92b4e-112">Downloads and installs the package into the current project, then update the project file to list the package as a dependency.</span></span> | [<span data-ttu-id="92b4e-113">Leitfaden für die Paket-Manager-Konsole</span><span class="sxs-lookup"><span data-stu-id="92b4e-113">Package Manager Console Guide</span></span>](../tools/Package-Manager-Console.md) |
| <span data-ttu-id="92b4e-114">Benutzeroberfläche des Paket-Managers (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="92b4e-114">Package Manager UI (Visual Studio)</span></span> | <span data-ttu-id="92b4e-115">Bietet eine Benutzeroberfläche, über die Sie die Liste der Pakete durchsuchen können, Pakete auswählen und in ein Projekt installieren können.</span><span class="sxs-lookup"><span data-stu-id="92b4e-115">Provides a UI through which you can browse, select, and install packages into a project.</span></span> <span data-ttu-id="92b4e-116">Aktualisiert die Projektdatei, damit das Paket als Abhängigkeit aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="92b4e-116">Updates the project file to list the package as a dependency.</span></span> | [<span data-ttu-id="92b4e-117">Referenz zur Benutzeroberfläche des Paket-Managers</span><span class="sxs-lookup"><span data-stu-id="92b4e-117">Package Manager UI Reference</span></span>](../tools/Package-Manager-UI.md) |