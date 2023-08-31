# AplicacaoWebDS
Aplicação Nivia de Quinta- feira

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;
using System.ComponentModel.DataAnnotations;

namespace AplicaçãoWebDS.Controllers
{
    public class Cliente
    {
        [Display(Name = "Nome do Cliente")]
        [Required(ErrorMessage = "Preencha seu Nome")]
        public string Nome { get; set; }

        [Display(Name = "Codigo do Cliente")]
        [Required(ErrorMessage = "Digite o Codigo do Cliente")]
        public int CodCliene { get; set; }

        [Display(Name = "Endereço")]
        [Required(ErrorMessage = "Digite o endereço")]
        public string Endereco { get; set; }

        [Display(Name = "Numero de Telefone")]
        [Required(ErrorMessage = "Digite seu Telefone")]
        [DataType(DataType.PhoneNumber)]
        public string Telefone { get; set; }

        [Display(Name = "Email")]
        [Required(ErrorMessage = "Digite seu Email")]
        [RegularExpression(@"\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*")]
        public string Email { get; set; }

        [Display(Name = "CPF")]
        [Required(ErrorMessage = "Digite seu CPF")]
        [StringLength(11)]
        public string CPF { get; set; }

        [Display(Name = "Data de Nascimento")]
        [Required(ErrorMessage = "Digite sua Data de Nascimento")]
        [DisplayFormat(DataFormatString = "{dd/mm/aaa}")]
        public DateTime DataNascimento { get; set; }
    }
}






@model AplicaçãoWebDS.Controllers.Cliente

@{
    ViewBag.Title = "index";
}

<h2>index</h2>


@using (Html.BeginForm())
{
    @Html.AntiForgeryToken()
    
    <div class="form-horizontal">
        <h4>Cliente</h4>
        <hr />
        @Html.ValidationSummary(true, "", new { @class = "text-danger" })
        <div class="form-group">
            @Html.LabelFor(model => model.Nome, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Nome, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.Nome, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.CodCliene, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.CodCliene, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.CodCliene, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Endereco, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Endereco, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.Endereco, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Telefone, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Telefone, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.Telefone, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Email, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Email, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.Email, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.CPF, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.CPF, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.CPF, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.DataNascimento, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.DataNascimento, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.DataNascimento, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            <div class="col-md-offset-2 col-md-10">
                <input type="submit" value="Save" class="btn btn-default" />
            </div>
        </div>
    </div>
}

<div>
    @Html.ActionLink("Back to List", "Index")
</div>

@section Scripts {
    @Scripts.Render("~/bundles/jqueryval")
}
