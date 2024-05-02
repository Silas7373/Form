@{
    ViewData["Title"] = "Anmeldung zur Aufnahme";
}
@using HTLAnmeldung.Models

@model RegistrationViewModel

<form asp-action="Register" method="post" class="needs-validation" >
    <div class="form-group">
        <label asp-for="Registration.Firstname"></label>
        <input asp-for="Registration.Firstname" class="form-control"  />
        <span asp-validation-for="Registration.Firstname" class="text-danger"></span>

    </div>
    <div class="form-group">
        <label asp-for="Registration.Lastname"></label>
        <input asp-for="Registration.Lastname" class="form-control" />
        <span asp-validation-for="Registration.Lastname" class="text-danger"></span>

    </div>
    <div class="form-group">
    <label asp-for="Registration.Email"></label>
    <input type="email" asp-for="Registration.Email" class="form-control" />
    <span asp-validation-for="Registration.Email" class="text-danger"></span>

    </div>

    <div class="form-group">
        <label asp-for="Registration.DateOfBirth"></label>
        <input asp-for="Registration.DateOfBirth" type="date" class="form-control"  />
        <span asp-validation-for="Registration.DateOfBirth" class="text-danger"></span>

    </div>
    <div class="form-group">
        <label asp-for="Registration.DepartmentId">Abteilungswunsch</label>
        <select asp-for="Registration.DepartmentId" asp-items="@((IEnumerable<SelectListItem>)ViewData["Abteilungswunsch"])" class="form-control" >
        </select>
        <div class="invalid-feedback">Bitte wählen Sie eine Abteilung aus.</div>
    </div>
    
    <button type="submit"  class="btn btn-primary">Anmelden</button>
</form>
@section Scripts{
    @{
        await Html.RenderPartialAsync("_ValidationScriptsPartial");
    }
}
