# HG-BYTRON-.
HG-BYTRON: Plataforma de Elite para Prestação de Serviços Técnicos.
import 'package:flutter/material.dart';

void main() => runApp(HGBytronApp());

class HGBytronApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      theme: ThemeData.dark(),
      home: ServiceScreen(),
    );
  }
}

class ServiceScreen extends StatelessWidget {
  // Cores extraídas das suas imagens
  final Color goldAccent = Color(0xFFD4AF37);
  final Color darkGrey = Color(0xFF1A1A1A);
  final Color neonYellow = Color(0xFFFFFF00);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.black,
      body: Stack(
        children: [
          // 1. Fundo com padrão de Hexágonos (simulado com imagem ou ícones)
          Positioned.fill(
            child: Opacity(
              opacity: 0.2,
              child: GridView.builder(
                gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(crossAxisCount: 5),
                itemBuilder: (context, index) => Icon(Icons.hexagon_outlined, color: goldAccent, size: 80),
              ),
            ),
          ),
          
          SafeArea(
            child: Column(
              children: [
                // Header
                Padding(
                  padding: const EdgeInsets.all(20.0),
                  child: Text(
                    "HG-BYTRON",
                    style: TextStyle(color: goldAccent, fontSize: 24, fontWeight: FontWeight.bold, letterSpacing: 2),
                  ),
                ),

                // Logo Central (Hexágono Iluminado)
                Container(
                  padding: EdgeInsets.all(20),
                  decoration: BoxDecoration(
                    shape: BoxShape.circle,
                    boxShadow: [BoxShadow(color: neonYellow.withOpacity(0.3), blurRadius: 40, spreadRadius: 10)],
                  ),
                  child: Icon(Icons.hexagon, size: 80, color: goldAccent),
                ),

                SizedBox(height: 20),

                // Card de Informações Estilo Metálico
                Padding(
                  padding: const EdgeInsets.symmetric(horizontal: 20),
                  child: Container(
                    decoration: BoxDecoration(
                      color: darkGrey,
                      borderRadius: BorderRadius.circular(15),
                      border: Border.all(color: goldAccent, width: 2),
                      boxShadow: [BoxShadow(color: Colors.black54, blurRadius: 10, offset: Offset(0, 5))],
                    ),
                    child: Column(
                      children: [
                        ListTile(
                          title: Text("Gabriel Atanásio Andessa", style: TextStyle(fontWeight: FontWeight.bold, color: Colors.white)),
                          subtitle: Text("Electrician, certified", style: TextStyle(color: goldAccent)),
                        ),
                        Divider(color: goldAccent.withOpacity(0.5)),
                        Padding(
                          padding: const EdgeInsets.all(15.0),
                          child: Text(
                            "Olá, vi seu perfil e gostaria de um orçamento para instalar um novo disjuntor.",
                            style: TextStyle(color: Colors.white70),
                          ),
                        ),
                      ],
                    ),
                  ),
                ),

                Spacer(),

                // Botão "CONFIRM APPOINTMENT"
                Padding(
                  padding: const EdgeInsets.all(20.0),
                  child: Container(
                    width: double.infinity,
                    height: 60,
                    decoration: BoxDecoration(
                      gradient: LinearGradient(colors: [goldAccent, Color(0xFF8B7500)]),
                      borderRadius: BorderRadius.horizontal(left: Radius.circular(5), right: Radius.circular(5)),
                      border: Border.all(color: Colors.white24, width: 3),
                    ),
                    child: Center(
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        children: [
                          Text("CONFIRM APPOINTMENT", style: TextStyle(color: Colors.black, fontWeight: FontWeight.black, fontSize: 18)),
                          SizedBox(width: 10),
                          Icon(Icons.calendar_month, color: Colors.black),
                        ],
                      ),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}
