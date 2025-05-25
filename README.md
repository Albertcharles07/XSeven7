import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { useState } from "react";
import { motion } from "framer-motion";
import { FaWolfPackBattalion } from "react-icons/fa";

export default function Xseven7() {
  const [email, setEmail] = useState("");
  const [username, setUsername] = useState("");
  const [password, setPassword] = useState("");

  const blogPosts = [
    {
      title: "5 hábitos diários para desbloquear sua mente",
      summary: "Descubra práticas simples que ajudam a fortalecer seu foco e clareza mental todos os dias."
    },
    {
      title: "Como vencer a procrastinação e agir com propósito",
      summary: "Saiba como transformar a procrastinação em produtividade com estratégias práticas."
    },
    {
      title: "O poder do silêncio: autoconhecimento na era da distração",
      summary: "Explore como momentos de silêncio podem revelar quem você realmente é."
    }
  ];

  return (
    <main className="min-h-screen bg-gradient-to-br from-gray-900 to-black text-white p-8 font-sans">
      <header className="flex items-center justify-between mb-12">
        <div className="flex items-center gap-3">
          <FaWolfPackBattalion className="text-4xl text-white" />
          <h1 className="text-3xl font-bold tracking-wide">Xseven7</h1>
        </div>
        <Button variant="outline" className="text-white border-white hover:bg-white hover:text-black">
          Entrar
        </Button>
      </header>

      <section className="text-center mb-20">
        <motion.h2
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6 }}
          className="text-5xl font-bold mb-4"
        >
          Desperte seu potencial interior
        </motion.h2>
        <p className="text-gray-300 max-w-2xl mx-auto mb-8">
          A Xseven7 é sua aliada na jornada do autoconhecimento, foco e crescimento pessoal. Liberte seu verdadeiro eu com ferramentas práticas e inspiração contínua.
        </p>
        <div className="flex justify-center gap-4 max-w-md mx-auto">
          <Input
            type="email"
            placeholder="Seu melhor e-mail"
            value={email}
            onChange={(e) => setEmail(e.target.value)}
            className="bg-white text-black"
          />
          <Button className="bg-white text-black hover:bg-gray-200">Quero receber novidades</Button>
        </div>
      </section>

      <section className="grid md:grid-cols-3 gap-6 mb-20">
        {[
          {
            title: "Autoconhecimento",
            text: "Descubra quem você realmente é e como transformar sua realidade."
          },
          {
            title: "Disciplina",
            text: "Desenvolva hábitos sólidos e mantenha o foco nos seus objetivos."
          },
          {
            title: "Alta Performance",
            text: "Técnicas e estratégias para viver no seu máximo potencial."
          }
        ].map((item, index) => (
          <Card key={index} className="bg-gray-800 text-white shadow-lg rounded-2xl">
            <CardContent className="p-6">
              <h3 className="text-xl font-semibold mb-2">{item.title}</h3>
              <p className="text-gray-300">{item.text}</p>
            </CardContent>
          </Card>
        ))}
      </section>

      <section className="max-w-4xl mx-auto mb-20 text-center">
        <h2 className="text-4xl font-bold mb-6">Sobre a Xseven7</h2>
        <p className="text-gray-300 mb-4">
          A Xseven7 nasceu com o propósito de despertar o lobo interior que existe em cada um de nós. Acreditamos no poder do autoconhecimento e da disciplina como chaves para uma vida plena e com propósito.
        </p>
        <p className="text-gray-300 mb-4">
          <strong>Missão:</strong> Guiar pessoas na jornada de transformação pessoal por meio de conteúdo de qualidade e ferramentas práticas.
        </p>
        <p className="text-gray-300 mb-4">
          <strong>Visão:</strong> Ser referência em desenvolvimento pessoal, criando uma comunidade de indivíduos comprometidos com sua evolução.
        </p>
        <p className="text-gray-300">
          <strong>Valores:</strong> Verdade, disciplina, liberdade e crescimento contínuo.
        </p>
      </section>

      <section className="max-w-5xl mx-auto mb-20">
        <h2 className="text-4xl font-bold text-center mb-10">Blog Xseven7</h2>
        <div className="grid md:grid-cols-3 gap-6">
          {blogPosts.map((post, index) => (
            <Card key={index} className="bg-gray-800 text-white rounded-2xl shadow-lg">
              <CardContent className="p-6">
                <h3 className="text-2xl font-semibold mb-2">{post.title}</h3>
                <p className="text-gray-300 mb-4">{post.summary}</p>
                <Button variant="outline" className="text-white border-white hover:bg-white hover:text-black">
                  Ler mais
                </Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      <section className="max-w-md mx-auto mb-20 text-center bg-gray-800 p-8 rounded-2xl shadow-xl">
        <h2 className="text-3xl font-bold mb-6">Área de Membros</h2>
        <Input
          type="text"
          placeholder="Usuário"
          value={username}
          onChange={(e) => setUsername(e.target.value)}
          className="mb-4 bg-white text-black"
        />
        <Input
          type="password"
          placeholder="Senha"
          value={password}
          onChange={(e) => setPassword(e.target.value)}
          className="mb-4 bg-white text-black"
        />
        <Button className="w-full bg-white text-black hover:bg-gray-200">Entrar</Button>
        <p className="text-sm text-gray-400 mt-4">Ainda não tem uma conta? <a href="#" className="underline">Cadastre-se</a></p>
      </section>
    </main>
  );
}

