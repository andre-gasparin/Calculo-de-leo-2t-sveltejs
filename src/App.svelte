<script>
	let litros = 10
	let proporsaoCombustivel = 30
	let proporsaoOleo = 1
	
	$: resultado = () => (litros * ( ((proporsaoOleo * 100) / proporsaoCombustivel) / 100)).toFixed(2).toString().replace(".", ",");
		
	
	
</script>
<style>
	.api-header {
		color: #fff;
		text-shadow: 0 2px 2px rgba(0,0,0,.9);
		background: #093028;  /* fallback for old browsers */
		background: -webkit-linear-gradient(to right, #237A57, #093028);  /* Chrome 10-25, Safari 5.1-6 */
		background: linear-gradient(to right, #237A57, #093028); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
		color:#fff;
		margin-bottom: 20px;
		border-radius: 0;
		border-bottom: 1px solid #fff;
	}
	.input-group-text{
		background: #093028; 
		color:#FFF;
	}
</style>

<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">



<div class="wrapper">
	<div class="content-page">
		<div class="content">
			<div class="container-fluid" style="max-width: 100%;text-align: center;padding: 0;">
				<div class="jumbotron api-header">
					<div class="container">
						<h1>Cálculadora de óleo 2 tempos</h1>
						<p>Calcule automaticamente a proporção de óleo e combustível para seu motor 2 tempos</p>
					</div>
				</div>
			</div>
			<div class="container-fluid">
				<div class="row" style="margin-top: 25px;">
					<div class="col-md-3"></div>
					<div class="col-md-6 well">
						<div class="card">
							<div class="card-body" style="position: relative;">
								<form class="calc" action="#" method="post">
									<p>A proporção está no manual de instruções ou/e em um adesivo próximo ao tanque. Ex.: 25:1</p>
									<div class="form-group">
									
										<div class="input-group proportion">
											<div class="input-group-prepend"><span class="input-group-text">Proporção: </span></div>
											<input type="number" class="form-control" id="ProporsaoCombustivel" bind:value={proporsaoCombustivel} >
											<div class="input-group-append"><span class="input-group-text">:</span></div>
											<input type="number" class="form-control" id="proporsaoOleo" bind:value={proporsaoOleo} placeholder="1">
										</div>
									</div>
									<hr>
									<h4>Combustível</h4>
									<p>Quantos litros de combustível você tem?</p>
									<div class="form-group">
										<div class="input-group">
											<input type="number" class="form-control" bind:value={litros} >
											<div class="input-group-append"><span class="input-group-text">litros</span></div>
										</div>
									</div>
									<hr>
									<h4>Quantidade de óleo 2t:</h4>
									<p class="results">Para tratar {litros} l de combustível ({proporsaoCombustivel}:{proporsaoOleo}), adicione <b>{resultado()}</b> litros de óleo.</p>
								</form>
							</div>
						</div>
					</div>
					<div class="col-md-3"></div>
				</div>
			</div>
		</div>
	</div>
</div>