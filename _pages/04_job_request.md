---
layout: page
title: Jomar Auto Glass - Cotización De Trabajo
permalink: /cotizacion/
metadescription: Jomar Auto Glass ofrece cambio de cristales para carros en Puerto Rico. Reemplazo de vidrios para autos. 
---

## Solicita Tu Cotización

<div class="bg-slate50 rounded-lg p-8 my-8">
  <p class="text-lg text-slate-700 leading-relaxed mb-4">
    Jomar Auto Glass ofrece cambio de cristales para carros en Puerto Rico con los mejores precios y servicio garantizado. Completa el formulario a continuación para recibir una cotización profesional.
  </p>
  <p class="text-slate-600">
    Te responderemos pronto con opciones de precio, disponibilidad de citas y detalles sobre nuestros servicios. También puedes llamar directamente o enviarnos una foto de tu vehículo.
  </p>
</div>

<form name="precioporpagina" id="precioporpagina" onsubmit="myButton.disabled = true; return true;" data-netlify="true" method="post" action="{{ site.baseurl }}/cotizacion_response/index.html">
	<input type="hidden" name="data-netlify" value="true" />
	<input type="hidden" name="Fecha" id="Fecha" />

	<fieldset>
	<legend>Su información</legend>	
	<div>
		<label for="Nombre">Nombre:</label>
		<input type="text" name="Nombre" id="Nombre" autofocus="true" />
	</div>
	<div>
		<label for="Correo_Electronico">Correo Electrónico: *</label>
		<input type="email" name="Correo_Electronico"  id="Correo_Electronico" required 
			oninvalid="this.setCustomValidity('Por favor, escriba su correo electrónico.')" 
			oninput="setCustomValidity('')" >
	</div>
	<div>
		<label for="Telefono">Teléfono:</label>
		<input type="tel" name="Telefono" id="Telefono" />
	</div>
	<div><br/>
		<label for="Localizado" style="width: 100%;">¿En que pueblo o ciudad está el auto localizado?</label>
		<textarea name="Localizado" id="Localizado" style="width:90%; height:60px"></textarea>
	</div>
	</fieldset>

	<br/>Jomar Auto Glass ofrece reemplazo de vidrios para autos y camiones. 

	<fieldset>
	<legend>Su Auto</legend>	
	<div>
		<label for="Ano">Año del Auto: *</label>
		<input type="text" name="Ano" id="Ano" required 
			oninvalid="this.setCustomValidity('Por favor, escriba el año de su auto.')" 
			oninput="setCustomValidity('')" >  
	</div>
	<div>
		<label for="Marca">Marca: *</label>
		<input type="text" name="Marca" id="Marca" required 
			oninvalid="this.setCustomValidity('Por favor, escriba la marca de su auto.')" 
			oninput="setCustomValidity('')" >
	</div>
	<div>
		<label for="Modelo">Modelo: *</label>
		<input type="text" name="Modelo" id="Modelo" required 
			oninvalid="this.setCustomValidity('Por favor, escriba el modelo de su auto.')" 
			oninput="setCustomValidity('')" >
	</div>
	<div>
		<label for="Delante_Tracero_Otro" style="vertical-align: top">¿Delantero, tracero? *</label>
		<select name="Delante_Tracero_Otro" id="Delante_Tracero_Otro" size="4" required 
			oninvalid="this.setCustomValidity('Por favor, indique que cristal está roto.')" 
			oninput="setCustomValidity('')" >
			<option value="Delantero">Delantero</option>
			<option value="Tracero">Tracero</option>
			<option value="Izquierdo">Izquierdo</option>
			<option value="Derecho">Derecho</option>
		</select>
	</div>
	<div>
		<br/>¿Número de puertas?<br/>
		<input type="radio" name="Numero_Puertas" value="Dos Puertas" style="width: 40px;">Dos
		<input type="radio" name="Numero_Puertas" value="Cuatro Puertas" style="width: 40px;">Cuatro
		<input type="checkbox" name="Hatchback" value="Si " style="width: 40px;">Hatchback?<br>
	</div>
	<div>
		<br/>¿Si escogió lado izquierdo o derecho, cual es su cristal roto?
	</div>
	<div class="row">
		<div class="column">
			<input type="radio" name="Cristal_Roto" value="Rear Quarter" style="width: 40px;">Rear Quarter<br>
			<input type="radio" name="Cristal_Roto" value="Rear Vent" style="width: 40px;">Rear Vent<br>
			<input type="radio" name="Cristal_Roto" value="Rear Door" style="width: 40px;">Rear Door<br>
			<input type="radio" name="Cristal_Roto" value="Front Door" style="width: 40px;">Front Door<br>
			<input type="radio" name="Cristal_Roto" value="Front Vent" style="width: 40px;">Front Vent<br><br>
			<input type="radio" name="Cristal_Roto" value="Tengo Duda" style="width: 40px;">Tengo Duda<br>
			&nbsp; &nbsp; &nbsp; (Explique abajo)<br>
		</div>
		<div class="column"><br/>
			<img src="/assets/pictures/carritocondetallescristales_1.png" alt="Carrito De Cristales" title="Carrito De Cristales">
		</div>
	</div>
	<div><br/>
		<label for="Informacion_Adicional" style="width: 100%;">Información Adicional</label>
		<textarea name="Informacion_Adicional" id="Informacion_Adicional" style="width:90%; height:60px"></textarea>
	</div>
	</fieldset>
	<div class="flex justify-center mt-8">
		<span class="error"><p id="Any_error"></p></span>
		<button type="submit" value="submit" name="myButton" class="bg-accent hover:bg-red-700 text-white font-heading font-bold py-3 px-8 rounded-lg transition uppercase tracking-wide">Enviar Cotización</button>
	</div>
</form>

---

## Otras Formas De Contactarnos

<div class="grid grid-cols-1 md:grid-cols-2 gap-8 my-12">
  <div class="bg-white rounded-lg shadow-sm border border-slate-200 p-6">
    <h3 class="font-heading font-bold text-lg text-primary mb-3">📧 Por Email</h3>
    <p class="text-slate-600 mb-4">
      Envía una foto de tu carro con el cristal roto a:
    </p>
    <a href="mailto:{{ site.email }}" class="inline-block bg-accent hover:bg-red-700 text-white font-heading font-bold py-2 px-4 rounded transition text-sm">
      {{ site.email }}
    </a>
    <p class="text-sm text-slate-500 mt-3">
      Pronto te devolveremos tu mensaje con detalles.
    </p>
  </div>

  <div class="bg-white rounded-lg shadow-sm border border-slate-200 p-6">
    <h3 class="font-heading font-bold text-lg text-primary mb-3">📞 Por Teléfono</h3>
    <p class="text-slate-600 mb-4">
      Llama directamente para hablar con nuestro equipo:
    </p>
    <a href="tel:{{ site.phones-link }}" class="inline-block bg-accent hover:bg-red-700 text-white font-heading font-bold py-2 px-4 rounded transition text-sm">
      {{ site.phones }}
    </a>
    <p class="text-sm text-slate-500 mt-3">
      Disponibles para responder todas tus preguntas.
    </p>
  </div>
</div>

<script type="text/javascript">
function getDate()
{
    var today = new Date();
    var dd = today.getDate();
    var mm = today.getMonth()+1; //January is 0!
    var yyyy = today.getFullYear();
    if(dd<10){dd='0'+dd} if(mm<10){mm='0'+mm}
    today = dd+"/"+mm+"/"+yyyy;

    document.getElementById("Fecha").value = today;
}

//call getDate() when loading the page
getDate();
</script>

