# Cuidandonos

## Integrantes
- Gary Ezequiel Berkman - 2034104 - gberkman@frba.utn.edu.ar
- Franco Smuraglia - 2040803 - fsmuraglia@frba.utn.edu.ar

### Link a LucidChart: https://lucid.app/lucidchart/2a8cd120-9990-448f-92e7-e7a3c502d332/edit?viewport_loc=-752%2C-601%2C3387%2C1590%2C0_0&invitationId=inv_2d0579c0-e134-470c-a712-cdfb11ea545c

## Código/Pseudocódigo que está en el LucidChart:

```
public Float calcularTiempoDemora(destinos) {
	return minutosDemora.stream().mapToFloat(Float::floatValue).sum(); }
```
```
public Float calcularTiempoDemora(destinos) {
  return 0;
}
```
```
abstract class EstadoViaje {
	protected Viaje viaje; 
 	public void EstadoViaje() {
    notificar();
  }
  public void notificar() {
    String mensaje = generarMensaje();
    ...
  }
  protected abstract String generarMensaje(); }
```
```
class EstadoComienzo {
  public void EstadoComienzo() {
    super();
    this.crearTimer()
  }
  protected String generarMensaje() {
    return "Viaje Comenzado";
  }
  public void calcularTiempoAproximado() {
    Float tiempoDemora = super.viaje.estrategiaDestino.calcularTiempoDemora(super.viaje.destinos);
	 	Float tiempoAproximado = tiempoDemora;

    for (int i = 0; i < super.viaje.destinos.size(); i++) {
      Direccion origen;
      if (i == 0) origen = super.viaje.dirOrigen;
      else origen = super.viaje.destinos[i - 1];

      tiempoAproximado += API.get(origen, super.viaje.destinos[i])
    }
    return tiempoAproximado;
}
public void crearTimer() {
  Float tiempo = this.calcularTiempoAproximado();
  super.viaje.setTiempoAproximado(tiempo);

  ScheduledExecutorService scheduler = Executors.newScheduledThreadPool(1);
  scheduler.schedule(super.viaje.detectarInterrupcion, tiempo, TimeUnit.SECONDS);
  }
}
```
