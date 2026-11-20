# Fundamentos teóricos — atmósfera terrestre

Este repositorio reúne la **parte atmosférica** de un taller de *Medios Continuos* (Universidad de Antioquia, 2025). El objetivo es explorar perfiles de la atmósfera terrestre obtenidos con **NRLMSISE-00** y compararlos con relaciones físicas simplificadas.

## 1. Modelo NRLMSISE-00

NRLMSISE-00 es un modelo **empírico de la atmósfera terrestre**, sensible a la altitud, la localización, el momento y las condiciones solares/geomagnéticas. En el notebook se consultan temperatura y densidad, y se construyen perfiles verticales.

## 2. Presión de un gas ideal

El notebook estima presión a partir de temperatura y densidad total mediante:

$$
P(z)\approx \rho(z)\frac{R_{\mathrm{gas}}T(z)}{M_{\mathrm{air}}}.
$$

El valor fijo de $M_{\mathrm{air}}$ es una **aproximación**, en particular fuera de la atmósfera baja.

## 3. Equilibrio hidrostático

$$
\frac{dP}{dz}=-\rho(z)g(z),\qquad
 g(z)=\frac{GM_\oplus}{(R_\oplus+z)^2}.
$$

El gradiente numérico de la presión aproximada se compara con el término $-\rho g$. Esta es una comprobación pedagógica del balance vertical, no una validación general de NRLMSISE-00.

## 4. Estimación de la tropopausa

El notebook busca un cambio de signo o un umbral en $dT/dz$ para obtener una **estimación simplificada** de la tropopausa. Este procedimiento no sustituye definiciones meteorológicas formales basadas en lapse rate.

## 5. Modelo simplificado de troposfera

$$
T(z)=T_0-Lz,\qquad h_0=\frac{T_0}{L}.
$$

Se realiza un ajuste de parámetros para aproximar los perfiles de temperatura, presión y densidad. En el código se usa una suma de desviaciones relativas cuadráticas denominada $\chi^2$; no es el estadístico chi-cuadrado usual basado en incertidumbres de medida.

## Alcance

Este trabajo estudia **la atmósfera de la Tierra**. No constituye una simulación de atmósferas exoplanetarias ni un análisis directo de habitabilidad planetaria. Las hipótesis y limitaciones del código se revisarán más adelante.
