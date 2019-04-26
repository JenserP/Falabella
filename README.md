# Falabella
Ejercicio práctico de automatización
	
  const {Selector} = require('testcafe')								
									
	fixture `First Test`								
									
	runner.browsers(['firefor','chrome']);								
									
	test('First Test - Realizar compra de un PS4', async function(t){								
		const buscar = Selector ('[name="q"]');							
		const btnbuscar = Selector ('[name="btnK"]');							
		const textofalabella = Selector ('.LC20lb');							
		const producto = Selector ('#searchQuestionSolr');							
		const btnproducto = Selector ('#searchFormSolr');							
		const ps4product = Selector ('.image');							
		const agregarbolsa = Selector ('button');							
		const verbolsa = Selector ('.fb-added-to-basket__ctas');							
		const btnplus = Selector ('button.fb-quantity-input__plus');							
		const experienceSelect = Selector ('.fb-inline-dropdown');							
		const experienceOption = experienceSelect.find('option');							
		const btncomprar = Selector ('.fb-order-status__cta');							
		await t							
			.navigateTo('http://www.google.com')						
			.typeText(buscar, 'falabella')						
			.click(btnbuscar)						
			.click(textofalabella)						
			.typeText(producto, 'PS4')						
			.click(btnproducto)						
			.click(ps4product)						
			.click(agregarbolsa)						
			.click(verbolsa)						
			.click(btnplus)						
			.click(experienceSelect).withText('2 años $ 59.590')						
			.click(btncomprar)						
	});	
