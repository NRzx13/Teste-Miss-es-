<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Missões do Casamento</title>
    <!-- Tailwind CSS para estilização rápida e moderna -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
</head>
<body class="bg-slate-50 text-slate-800 font-sans p-4 max-w-md mx-auto">

    <div class="text-center my-6">
        <h1 class="text-2xl font-bold text-rose-600">📸 Caça ao Tesouro do Casamento</h1>
        <p class="text-sm text-slate-600 mt-1">Cumpra as missões, envie suas fotos e dispute o prêmio!</p>
    </div>

    <!-- Identificação do Convidado -->
    <div class="bg-white p-4 rounded-xl shadow-sm mb-4 border border-slate-100">
        <label class="block text-xs font-semibold uppercase text-slate-500 mb-1">Seu Nome / Família:</label>
        <input type="text" id="nomeConvidado" placeholder="Ex: João e Maria" class="w-full p-2 border rounded-lg text-sm focus:ring-2 focus:ring-rose-500 outline-none">
    </div>

    <!-- Lista de Missões (Exemplo estático que viria do Banco de Dados) -->
    <div id="listaMissoes" class="space-y-4">
        <!-- Missão 1 -->
        <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-100">
            <div class="flex justify-between items-center mb-2">
                <h3 class="font-semibold text-slate-800">Brinde com os Noivos</h3>
                <span class="bg-rose-100 text-rose-700 text-xs font-bold px-2 py-1 rounded-full">+30 pts</span>
            </div>
            <p class="text-xs text-slate-500 mb-3">Tire uma foto brindando com os noivos na mesa ou pista.</p>
            
            <!-- Input de Arquivo (Abre a câmera no celular) -->
            <input type="file" accept="image/*" capture="environment" id="foto-1" class="block w-full text-xs text-slate-500 file:mr-4 file:py-2 file:px-4 file:rounded-full file:border-0 file:text-xs file:font-semibold file:bg-rose-50 file:text-rose-700 hover:file:bg-rose-100 mb-2">
            
            <button onclick="enviarMissao(1)" class="w-full bg-rose-600 text-white py-2 rounded-lg text-sm font-semibold hover:bg-rose-700 transition">Enviar Foto</button>
        </div>
    </div>

    <script>
        function enviarMissao(missaoId) {
            const nome = document.getElementById('nomeConvidado').value;
            const inputFoto = document.getElementById(`foto-${missaoId}`);
            
            if(!nome) {
                alert('Por favor, digite seu nome antes de enviar a foto!');
                return;
            }
            if(inputFoto.files.length === 0) {
                alert('Selecione ou tire uma foto primeiro!');
                return;
            }

            alert(`Enviando foto da missão ${missaoId} para o sistema de ${nome}! (Aqui entra a integração com o Supabase Storage e Database)`);
            // Na programação real, você faria o upload para o Supabase Storage 
            // e salvaria o link gerado na tabela 'envios'.
        }
    </script>
</body>
</html>
