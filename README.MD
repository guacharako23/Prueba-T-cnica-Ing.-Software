pruebascrapy

Se requiere realizar un proceso de Web scraping o raspado de datos.


# Primeros pasos
    Tener instalado un IDE 
    Tener instalado python y pip

# instalar ambiente virtual
    pip install virtualenv

# crear ambiente virtual
    virtualenv venv

# Activar y desactivar ambiente virtual
    venv\Scripts\activate
    venv\Scripts\deactivate

# Instalar requerimientos
    pip install -r requirements.txt

    -- Verificar scrapy
    scrapy version

# crear proyecto con scrapy
    scrapy startproject ejercicio_scrapy
    cd ejercicio_scrapy

# Pagina solicitada para el desarrollo del ejecicio
https://superargo.supersalud.gov.co/formularioWeb/pqrd.php

# xpath Referencias para acceder a los elementos en la consola del navegador
    $x("//input[@id='nombre_afectado_1']")
    $x("//input[@id='nombre_afectado_2']")
    $x("//input[@id='apellidos_afectado_1']")
    $x("//input[@id='apellidos_afectado_2']")
    $x("//input[@id='fecha_nacimiento']")
    $x("//input[@id='edad']")

# verificar xpath por la consola de scrapy
    scrapy shell "https://superargo.supersalud.gov.co/formularioWeb/pqrd.php"

      primernombre =   response.xpath(("//input[@id='nombre_afectado_1']")[0].value).getall()
      segundonombre=   response.xpath(("//input[@id='nombre_afectado_2']")[0].value).getall()
      primerapellido=  response.xpath(("//input[@id='apellidos_afectado_1']")[0].value).getall()
      segundoapellido= response.xpath(("//input[@id='apellidos_afectado_2']")[0].value).getall()
      fechanacimiento= response.xpath(("//input[@id='fecha_nacimiento']")[0].value).getall()
      edad= response.xpath(("//input[@id='edad']")[0].value).getall()
    
# Generar nuestro archivo a partir de nuestro spider
    scrapy crawl 'datos'