
<script>
    import { Col, Container, Row } from 'sveltestrap';
    import CreciFrameBotao from './CreciFrameBotao.svelte';
    import Footer from './Footer.svelte';
</script>
<main>
    <div class="pseudo-body h-100 d-flex flex-column justify-content-evenly align-items-center">
        <Container class="wrapper h-100 border rounded-0 d-flex flex-column" style="min-width:40%;max-width:76.5%;">
            <div class="layout justify-content-center align-items-center d-flex flex-grow-1 flex-column h-100">
                <Container class="d-flex flex-column justify-content-evenly h-100">
                    <Row class="image-row justify-content-center">
                        <Col md="6">
                            <img src="http://crecise.gov.br/wp-content/themes/creci-sergipe-top/img/creci-logo.png" class="img-fluid" alt="Creci Imagem"/>
                        </Col>
                    </Row>
                    <Row class="text-row mt-3">
                        <p class="fw-bolder h3 text-center"> Escolha uma das opções abaixo para iniciar: </p>
                    </Row>
                    <Row class="button-1-row justify-content-center align-items-center mt-3 gx-0">
                        <Col md="4" class="text-center">
                           <CreciFrameBotao href="/armarios" text="Armários"></CreciFrameBotao>
                        </Col>
                        <Col md="4" class="text-center">
                            <CreciFrameBotao href="#" text="Clica aqui"></CreciFrameBotao>
                        </Col>
                        <Col md="4" class="text-center">
                            <CreciFrameBotao href="#" text="Clica aqui"></CreciFrameBotao>
                        </Col>
                    </Row>
                    <Row class="button-2-row justify-content-center align-items-center mt-3 gx-0">
                        <Col md="4" class="text-center">
                            <CreciFrameBotao href="#" text="Clica aqui">
                            </CreciFrameBotao>
                        </Col>
                        <Col md="4" class="text-center">
                            <CreciFrameBotao href="#" text="Clica aqui"></CreciFrameBotao>
                        </Col>
                        <Col md="4" class="text-center">
                            <CreciFrameBotao href="#" text="Clica aqui"></CreciFrameBotao>
                        </Col>
                    </Row>
                </Container>
            </div>
        </Container>
    </div>
</main>
<style>
main {
    height:80%;
}

</style>
