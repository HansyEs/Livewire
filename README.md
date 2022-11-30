# Livewire
### Para generar un PDF (con "barryvdh/laravel-dompdf") y devolverlo en un método del livewire es necesario...
            // Crear el PDF con la vista como siempre
            $pdf = PDF::loadView($this->path."/".$this->templatePath."/sea-waybill", [ 'data' => $data ]);
            $pdf->setPaper('A4', 'portrait');
            $pdf = $pdf->output();
            // Devolver la respuesta en el livewire
            return response()->streamDownload(fn() => print($pdf, 'Nombre del PDF.pdf');
