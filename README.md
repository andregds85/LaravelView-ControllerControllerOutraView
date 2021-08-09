# LaravelView-ControllerControllerOutraView
LaravelView  Controller Controller OutraView






Laravel - View Controller / Controlller view


Exemplo 1 
Parte 1 
       View que vai Imprimir   Da view envia o ID para o Método show do Controller
<td>  <a class="btn btn-info" href="{{ route('checklistadm.show',$t->id) }}">Vizualizar</a>


O retorno da Função envia o ID Direto para view 
Parte 2     
      Metodo Show do Laravel 
        

    public function show($id)
    {
        return view('checklistTransporte.mypdf',['id'=>$id]);

    }

   
   
    Exemplo 2 
     View que vai imprimir envia o id via url para o controller 
      <a class="btn btn-info" href="{{ url('checklistpdf',$t->id) }}">Imprimir PDF</a></td>

Parte 2 
     Na linha de $pdf ele manda id do controller para view 


Na 
public function generatePDF($id)
    {
        $data = [
            'title' => 'Checklist Transporte Seguro',
            'date' => date('d/m/Y')
        ];
          
        $pdf = PDF::loadView('checklistTransporte.mypdf',['id'=>$id]);
        return $pdf->download('ChecklistTransporteSeguro.pdf');
    }


}
