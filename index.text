import { useEffect, useState } from "react";
import { Link } from "react-router-dom";
import heroImg from "@/assets/hero-barbershop.jpg";
import { Logo } from "@/components/Logo";
import { AnnouncementCard } from "@/components/AnnouncementCard";
import { Announcement, getAnnouncements } from "@/lib/storage";
import { Instagram, MapPin, Phone } from "lucide-react";

const BENEFITS = [
  {
    n: "01",
    title: "Primera visita",
    desc: "Tu primer corte te otorga un 20% de descuento para tu próxima visita.",
    badge: "20% off",
  },
  {
    n: "02",
    title: "Cliente recurrente",
    desc: "Entre la segunda y tercera visita ingresas a nuestro programa de seguimiento personalizado.",
    badge: "Seguimiento",
  },
  {
    n: "03",
    title: "Cliente fiel",
    desc: "A partir de tu cuarta visita, tu próximo corte es completamente gratis. Es nuestra forma de agradecer.",
    badge: "Corte gratis",
  },
];

export default function Index() {
  const [announcements, setAnnouncements] = useState<Announcement[]>([]);

  useEffect(() => {
    setAnnouncements(getAnnouncements());
  }, []);

  return (
    <div className="min-h-screen bg-cream text-noir">
      {/* Top bar */}
      <header className="hairline-b">
        <div className="container flex items-center justify-between py-5">
          <Logo />
          <nav className="hidden md:flex items-center gap-8 text-xs uppercase tracking-luxury">
            <a href="#beneficios" className="hover:text-gold transition-colors">Beneficios</a>
            <a href="#anuncios" className="hover:text-gold transition-colors">Anuncios</a>
            <a href="#contacto" className="hover:text-gold transition-colors">Contacto</a>
          </nav>
        </div>
      </header>

      {/* Hero */}
      <section className="relative">
        <div className="container grid md:grid-cols-2 gap-10 md:gap-16 py-16 md:py-28 items-center">
          <div>
            <div className="text-[10px] uppercase tracking-luxury text-gold mb-6">
              Barbería · Desde 2018
            </div>
            <h1 className="font-serif text-5xl md:text-7xl leading-[1.05] mb-6">
              El arte del<br />
              <span className="italic text-gold">corte</span> con carácter.
            </h1>
            <p className="text-base md:text-lg font-light text-foreground/70 max-w-md leading-relaxed mb-10">
              En J. Llantoy cada corte es una pieza pensada para ti. Estilo, precisión
              y un programa de fidelidad que premia tu lealtad.
            </p>
            <div className="flex items-center gap-6">
              <a
                href="#beneficios"
                className="inline-flex items-center gap-3 px-7 py-4 bg-noir text-cream text-xs uppercase tracking-luxury hover:bg-gold hover:text-noir transition-colors"
              >
                Ver beneficios
              </a>
              <a
                href="#anuncios"
                className="inline-flex items-center gap-2 text-xs uppercase tracking-luxury text-foreground/70 hover:text-gold transition-colors"
              >
                <span className="h-px w-6 bg-current" />
                Anuncios
              </a>
            </div>
          </div>

          <div className="relative">
            <div className="hairline-gold p-2">
              <img
                src={heroImg}
                alt="Interior de la barbería J. Llantoy"
                width={1600}
                height={1024}
                className="w-full h-[420px] md:h-[520px] object-cover"
              />
            </div>
            <div className="absolute -bottom-6 -left-6 bg-noir text-cream px-6 py-4 hairline-gold">
              <div className="text-[10px] uppercase tracking-luxury text-gold">Establecido</div>
              <div className="font-serif text-2xl">MMXVIII</div>
            </div>
          </div>
        </div>
      </section>

      {/* Benefits */}
      <section id="beneficios" className="bg-noir text-cream py-20 md:py-28">
        <div className="container">
          <div className="max-w-2xl mb-16">
            <div className="text-[10px] uppercase tracking-luxury text-gold mb-4">
              Programa de fidelidad
            </div>
            <h2 className="font-serif text-4xl md:text-5xl leading-tight">
              Tu lealtad <span className="italic text-gold">recompensada</span>.
            </h2>
            <p className="mt-6 text-cream/70 font-light max-w-lg">
              Un sistema simple que reconoce y agradece a cada cliente que regresa.
            </p>
          </div>

          <div className="grid md:grid-cols-3 gap-px bg-gold/30">
            {BENEFITS.map((b) => (
              <div
                key={b.n}
                className="bg-noir p-10 md:p-12 group hover:bg-gold/5 transition-colors"
              >
                <div className="flex items-baseline justify-between mb-8">
                  <span className="font-serif text-5xl text-gold">{b.n}</span>
                  <span className="text-[10px] uppercase tracking-luxury text-gold border border-gold/40 px-3 py-1">
                    {b.badge}
                  </span>
                </div>
                <h3 className="font-serif text-2xl mb-3">{b.title}</h3>
                <p className="text-sm font-light text-cream/70 leading-relaxed">
                  {b.desc}
                </p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Announcements */}
      <section id="anuncios" className="py-20 md:py-28">
        <div className="container">
          <div className="flex items-end justify-between mb-12">
            <div>
              <div className="text-[10px] uppercase tracking-luxury text-gold mb-4">
                Desde la silla
              </div>
              <h2 className="font-serif text-4xl md:text-5xl">
                Lo último en J. Llantoy
              </h2>
            </div>
          </div>

          {announcements.length === 0 ? (
            <div className="hairline-gold p-12 md:p-16 text-center max-w-2xl mx-auto">
              <div className="text-[10px] uppercase tracking-luxury text-gold mb-4">
                Pronto
              </div>
              <h3 className="font-serif text-3xl md:text-4xl mb-3">
                Próximamente, novedades.
              </h3>
              <p className="text-foreground/60 font-light">
                Estamos preparando anuncios especiales para nuestros clientes. Vuelve
                pronto para descubrirlos.
              </p>
            </div>
          ) : (
            <div className="grid md:grid-cols-2 gap-6">
              {announcements
                .slice()
                .reverse()
                .map((a) => (
                  <AnnouncementCard key={a.id} a={a} />
                ))}
            </div>
          )}
        </div>
      </section>

      {/* Footer */}
      <footer id="contacto" className="hairline-t bg-cream">
        <div className="container py-14 grid md:grid-cols-3 gap-10">
          <div>
            <Logo />
            <p className="mt-4 text-sm font-light text-foreground/60 max-w-xs">
              Barbería de carácter. Cortes pensados, atención personal.
            </p>
          </div>
          <div className="space-y-3 text-sm font-light">
            <div className="text-[10px] uppercase tracking-luxury text-gold mb-3">Contacto</div>
            <div className="flex items-center gap-3">
              <Phone className="w-3.5 h-3.5 text-gold" />
              <span>+51 987 654 321</span>
            </div>
            <div className="flex items-center gap-3">
              <MapPin className="w-3.5 h-3.5 text-gold" />
              <span>Av. Principal 123, Lima</span>
            </div>
            <div className="flex items-center gap-3">
              <Instagram className="w-3.5 h-3.5 text-gold" />
              <span>@jllantoy.barber</span>
            </div>
          </div>
          <div className="space-y-3 text-sm font-light">
            <div className="text-[10px] uppercase tracking-luxury text-gold mb-3">Horario</div>
            <div className="flex justify-between max-w-[220px]"><span>Lun – Vie</span><span>10:00 – 21:00</span></div>
            <div className="flex justify-between max-w-[220px]"><span>Sábado</span><span>10:00 – 22:00</span></div>
            <div className="flex justify-between max-w-[220px]"><span>Domingo</span><span>11:00 – 18:00</span></div>
          </div>
        </div>
        <div className="hairline-t">
          <div className="container py-6 flex items-center justify-between text-[10px] uppercase tracking-luxury text-foreground/50">
            <span>© {new Date().getFullYear()} J. Llantoy</span>
            {/* Hidden barber access */}
            <Link
              to="/barber"
              aria-label="Acceso interno"
              className="text-foreground/20 hover:text-gold transition-colors"
              title="·"
            >
              ·
            </Link>
          </div>
        </div>
      </footer>
    </div>
  );
}
