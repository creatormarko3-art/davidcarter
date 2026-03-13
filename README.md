import heroImage from "@/assets/hero-dad.jpg";
import { Button } from "@/components/ui/button";
import { Check, Dumbbell, Flame, Clock, Users, Star, ChevronRight, Zap, UtensilsCrossed, BarChart3, BookOpen } from "lucide-react";

const CTAButton = ({ children, className = "" }: { children: React.ReactNode; className?: string }) => (
  <Button variant="cta" size="lg" className={`h-14 px-10 text-lg ${className}`}>
    {children} <ChevronRight className="ml-1" />
  </Button>
);

const HeroSection = () => (
  <section className="relative min-h-screen flex items-center overflow-hidden">
    <div className="absolute inset-0 bg-gradient-to-r from-background via-background/95 to-background/40 z-10" />
    <img src={heroImage} alt="Transformed dad" className="absolute right-0 top-0 h-full w-1/2 object-cover object-center opacity-60 md:opacity-80" />
    <div className="container relative z-20 py-20">
      <div className="max-w-2xl space-y-6">
        <span className="inline-block border border-primary/30 bg-primary/10 text-primary px-4 py-1.5 rounded-full text-sm font-medium tracking-wide uppercase font-display">
          90-Day Transformation
        </span>
        <h1 className="text-5xl md:text-7xl font-bold leading-[0.95] text-foreground">
          From <span className="text-gradient-gold">Dad Bod</span> to
          <br />
          <span className="text-gradient-gold">Dad Strong</span>
        </h1>
        <p className="text-lg text-muted-foreground max-w-lg leading-relaxed">
          The simple 90-day system that helped a 52-year-old father lose the gut, build real strength, and get his confidence back. No gym bro science. No extreme diets.
        </p>
        <div className="flex flex-col sm:flex-row gap-4 pt-2">
          <CTAButton>Start Your Glow-Up</CTAButton>
          <div className="flex items-center gap-2 text-muted-foreground">
            <span className="text-2xl font-display font-bold text-primary">$10</span>
            <span className="text-sm">one-time<br/>payment</span>
          </div>
        </div>
        <div className="flex gap-6 pt-4 text-sm text-muted-foreground">
          <span className="flex items-center gap-1.5"><Check className="w-4 h-4 text-primary" /> 90-Day Plan</span>
          <span className="flex items-center gap-1.5"><Check className="w-4 h-4 text-primary" /> Meal Guide</span>
          <span className="flex items-center gap-1.5"><Check className="w-4 h-4 text-primary" /> Progress Tracker</span>
        </div>
      </div>
    </div>
  </section>
);

const ProblemSection = () => {
  const problems = [
    { icon: Flame, title: "Belly Fat Won't Budge", desc: "You've tried cutting calories, skipping meals, even those late-night ab workouts. Nothing sticks." },
    { icon: Zap, title: "Zero Energy", desc: "You're running on coffee and willpower. By 3pm you're done. Weekends are for recovering, not living." },
    { icon: Clock, title: "No Time", desc: "Between work, kids, and everything else, there's no time left for a 2-hour gym session." },
    { icon: Users, title: "Losing Confidence", desc: "You avoid mirrors. Old photos remind you of a different person. You want that guy back." },
  ];

  return (
    <section className="section-darker py-24">
      <div className="container">
        <div className="text-center max-w-2xl mx-auto mb-16">
          <h2 className="text-4xl md:text-5xl font-bold mb-4">Sound <span className="text-gradient-gold">Familiar?</span></h2>
          <p className="text-muted-foreground text-lg">You're not lazy. You're not broken. You just don't have the right system.</p>
        </div>
        <div className="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
          {problems.map((p) => (
            <div key={p.title} className="bg-card border-gradient-gold rounded-xl p-6 flex gap-4">
              <div className="w-12 h-12 rounded-lg bg-primary/10 flex items-center justify-center flex-shrink-0">
                <p.icon className="w-6 h-6 text-primary" />
              </div>
              <div>
                <h3 className="text-lg font-display font-semibold mb-1 text-foreground">{p.title}</h3>
                <p className="text-muted-foreground text-sm leading-relaxed">{p.desc}</p>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const StorySection = () => (
  <section className="section-dark py-24">
    <div className="container max-w-4xl">
      <div className="grid md:grid-cols-[300px_1fr] gap-12 items-center">
        <div className="relative">
          <img src={heroImage} alt="David Carter" className="rounded-xl border-gradient-gold w-full" />
          <div className="absolute -bottom-4 -right-4 bg-primary text-primary-foreground px-4 py-2 rounded-lg font-display font-bold text-sm">
            AGE 52
          </div>
        </div>
        <div className="space-y-5">
          <h2 className="text-4xl md:text-5xl font-bold">Meet <span className="text-gradient-gold">David Carter</span></h2>
          <p className="text-muted-foreground leading-relaxed">
            At 52, David was 40 pounds overweight, exhausted every day, and couldn't keep up with his kids. He'd tried every diet, every app, every "quick fix." Nothing worked because nothing was built for a real dad's life.
          </p>
          <p className="text-muted-foreground leading-relaxed">
            So he built his own system. Simple workouts he could do in 30 minutes. Meals his family would actually eat. A daily tracker that kept him honest.
          </p>
          <p className="text-foreground font-medium text-lg">
            90 days later, he lost 35 pounds, doubled his energy, and his kids started calling him "the strong dad."
          </p>
          <p className="text-muted-foreground leading-relaxed">
            Now he's sharing exactly what he did — so you can do it too.
          </p>
        </div>
      </div>
    </div>
  </section>
);

const WhatYouGetSection = () => {
  const items = [
    { icon: Dumbbell, title: "90-Day Workout Plan", desc: "3 beginner-friendly workouts per week. 30 minutes each. No gym required.", tag: "Core" },
    { icon: UtensilsCrossed, title: "Simple Meal Plan", desc: "Easy meals your family will eat too. Includes meal prep guide and grocery lists.", tag: "Nutrition" },
    { icon: BarChart3, title: "Progress Tracker", desc: "Notion template to track workouts, meals, weight, and wins. See your progress daily.", tag: "Tracking" },
    { icon: BookOpen, title: "Step-by-Step Guide", desc: "Practical tips for sleep, energy, discipline, and building habits that last.", tag: "Habits" },
  ];

  return (
    <section className="section-darker py-24">
      <div className="container">
        <div className="text-center max-w-2xl mx-auto mb-16">
          <h2 className="text-4xl md:text-5xl font-bold mb-4">Everything You <span className="text-gradient-gold">Need</span></h2>
          <p className="text-muted-foreground text-lg">No fluff. No filler. Just a proven system that works for real dads.</p>
        </div>
        <div className="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
          {items.map((item) => (
            <div key={item.title} className="bg-card border-gradient-gold rounded-xl p-8 space-y-3 hover:glow-gold transition-shadow duration-500">
              <div className="flex items-center gap-3">
                <div className="w-10 h-10 rounded-lg bg-primary/10 flex items-center justify-center">
                  <item.icon className="w-5 h-5 text-primary" />
                </div>
                <span className="text-xs font-display uppercase tracking-widest text-primary">{item.tag}</span>
              </div>
              <h3 className="text-xl font-display font-bold text-foreground">{item.title}</h3>
              <p className="text-muted-foreground text-sm leading-relaxed">{item.desc}</p>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const WhyItWorksSection = () => {
  const reasons = [
    { stat: "3x", label: "Workouts / Week", desc: "That's it. No 6-day splits." },
    { stat: "30", label: "Minutes Each", desc: "Shorter than a Netflix episode." },
    { stat: "0", label: "Gym Memberships", desc: "Do it at home. Or the garage." },
    { stat: "100%", label: "Dad Approved", desc: "Built around jobs, kids, and real life." },
  ];

  return (
    <section className="section-dark py-24">
      <div className="container">
        <div className="text-center max-w-2xl mx-auto mb-16">
          <h2 className="text-4xl md:text-5xl font-bold mb-4">Why This <span className="text-gradient-gold">Works</span></h2>
          <p className="text-muted-foreground text-lg">It's not about doing more. It's about doing the right things consistently.</p>
        </div>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-6 max-w-4xl mx-auto">
          {reasons.map((r) => (
            <div key={r.label} className="text-center space-y-2 p-6">
              <div className="text-5xl font-display font-bold text-gradient-gold">{r.stat}</div>
              <div className="text-sm font-display uppercase tracking-wider text-foreground">{r.label}</div>
              <div className="text-xs text-muted-foreground">{r.desc}</div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const TestimonialsSection = () => {
  const testimonials = [
    { name: "Mike R., 41", text: "I've tried everything. This is the first program I actually finished. Down 22 lbs and my wife noticed in week 3.", stars: 5 },
    { name: "Jason T., 38", text: "30-minute workouts that actually work? Sign me up. I'm in the best shape I've been since college.", stars: 5 },
    { name: "Carlos M., 55", text: "I thought getting fit after 50 was impossible. David's system proved me wrong. My energy is through the roof.", stars: 5 },
  ];

  return (
    <section className="section-darker py-24">
      <div className="container">
        <div className="text-center max-w-2xl mx-auto mb-16">
          <h2 className="text-4xl md:text-5xl font-bold mb-4">Dads Who <span className="text-gradient-gold">Did It</span></h2>
        </div>
        <div className="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">
          {testimonials.map((t) => (
            <div key={t.name} className="bg-card border-gradient-gold rounded-xl p-8 space-y-4">
              <div className="flex gap-1">
                {Array.from({ length: t.stars }).map((_, i) => (
                  <Star key={i} className="w-4 h-4 text-primary fill-primary" />
                ))}
              </div>
              <p className="text-foreground text-sm leading-relaxed italic">"{t.text}"</p>
              <p className="text-muted-foreground text-sm font-display font-semibold">— {t.name}</p>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const PricingSection = () => (
  <section className="section-dark py-24">
    <div className="container">
      <div className="max-w-lg mx-auto text-center">
        <h2 className="text-4xl md:text-5xl font-bold mb-4">Get Started <span className="text-gradient-gold">Today</span></h2>
        <p className="text-muted-foreground text-lg mb-10">Less than the cost of a single fast food meal. More value than a $200/month gym membership.</p>
        <div className="bg-card border-gradient-gold rounded-2xl p-10 glow-gold space-y-6">
          <div className="font-display">
            <span className="text-6xl font-bold text-gradient-gold">$10</span>
            <span className="text-muted-foreground text-lg ml-2">one-time</span>
          </div>
          <ul className="space-y-3 text-left max-w-xs mx-auto">
            {[
              "90-Day Workout Plan",
              "Simple Meal Plan & Prep Guide",
              "Notion Progress Tracker",
              "Step-by-Step Habit Guide",
              "Lifetime Access",
            ].map((item) => (
              <li key={item} className="flex items-center gap-3 text-foreground text-sm">
                <Check className="w-5 h-5 text-primary flex-shrink-0" />
                {item}
              </li>
            ))}
          </ul>
          <CTAButton className="w-full">Start Your Dad Glow-Up</CTAButton>
          <p className="text-xs text-muted-foreground">Instant digital delivery. No subscriptions. No BS.</p>
        </div>
      </div>
    </div>
  </section>
);

const FinalCTASection = () => (
  <section className="section-darker py-24">
    <div className="container text-center max-w-2xl mx-auto space-y-6">
      <h2 className="text-4xl md:text-5xl font-bold">Your Kids Are <span className="text-gradient-gold">Watching</span></h2>
      <p className="text-muted-foreground text-lg leading-relaxed">
        Every day you wait is another day your kids see a dad who gave up on himself. Be the dad who showed up. Be the dad who changed. Be the dad they want to become.
      </p>
      <div className="pt-4">
        <CTAButton>Start Your Glow-Up — $10</CTAButton>
      </div>
      <p className="text-xs text-muted-foreground pt-4">Join hundreds of dads who already took the first step.</p>
    </div>
  </section>
);

const Footer = () => (
  <footer className="border-t border-border py-8">
    <div className="container text-center text-xs text-muted-foreground">
      © {new Date().getFullYear()} Dad Glow-Up System. All rights reserved.
    </div>
  </footer>
);

const Index = () => {
  return (
    <div className="min-h-screen">
      <HeroSection />
      <ProblemSection />
      <StorySection />
      <WhatYouGetSection />
      <WhyItWorksSection />
      <TestimonialsSection />
      <PricingSection />
      <FinalCTASection />
      <Footer />
    </div>
  );
};

export default Index;
