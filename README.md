import React, { useState } from 'react';
import { 
  ChevronRight, Play, CheckCircle, Home, Layout, 
  Building2, Hammer, ArrowRight, Menu, X, Star 
} from 'lucide-react';

const Navbar = () => {
  const [isOpen, setIsOpen] = useState(false);

  const closeMenu = () => setIsOpen(false);

  return (
    <nav className="fixed w-full z-50 bg-black/60 backdrop-blur-lg border-b border-white/10 transition-all duration-300">
      <div className="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
        <div className="text-white font-serif text-2xl tracking-widest uppercase">
          Studio<span className="text-amber-500">.</span>
        </div>
        
        <div className="hidden md:flex space-x-8 text-sm font-medium tracking-wide text-gray-300">
          <a href="#about" className="hover:text-amber-500 transition-colors">About</a>
          <a href="#services" className="hover:text-amber-500 transition-colors">Services</a>
          <a href="#portfolio" className="hover:text-amber-500 transition-colors">Portfolio</a>
          <a href="#testimonials" className="hover:text-amber-500 transition-colors">Clients</a>
        </div>

        <div className="hidden md:flex">
          <a href="#contact" className="bg-amber-600 hover:bg-amber-700 text-white px-6 py-2.5 text-sm uppercase tracking-wider transition-colors duration-300">
            Get a Quote
          </a>
        </div>

        <button 
          className="md:hidden text-white" 
          onClick={() => setIsOpen(!isOpen)}
          aria-label={isOpen ? "Close navigation menu" : "Open navigation menu"}
          aria-expanded={isOpen}
          aria-controls="mobile-menu"
        >
          {isOpen ? <X size={28} /> : <Menu size={28} />}
        </button>
      </div>

      {/* Mobile Menu Dropdown */}
      {isOpen && (
        <div 
          id="mobile-menu"
          className="md:hidden bg-black/95 backdrop-blur-lg border-t border-white/10 p-6 space-y-4"
          role="navigation"
        >
          <a href="#about" onClick={closeMenu} className="block text-gray-300 hover:text-amber-500 transition-colors text-sm uppercase tracking-wide">About</a>
          <a href="#services" onClick={closeMenu} className="block text-gray-300 hover:text-amber-500 transition-colors text-sm uppercase tracking-wide">Services</a>
          <a href="#portfolio" onClick={closeMenu} className="block text-gray-300 hover:text-amber-500 transition-colors text-sm uppercase tracking-wide">Portfolio</a>
          <a href="#testimonials" onClick={closeMenu} className="block text-gray-300 hover:text-amber-500 transition-colors text-sm uppercase tracking-wide">Clients</a>
          <a href="#contact" onClick={closeMenu} className="block bg-amber-600 hover:bg-amber-700 text-white px-6 py-2.5 text-sm uppercase tracking-wider transition-colors duration-300 text-center">Get a Quote</a>
        </div>
      )}
    </nav>
  );
};

const Hero = () => {
  return (
    <section className="relative h-screen flex items-center justify-center overflow-hidden" aria-label="Hero section">
      <div 
        className="absolute inset-0 bg-cover bg-center bg-no-repeat scale-105 animate-pulse-slow"
        style={{ backgroundImage: 'url("https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80")' }}
        role="img"
        aria-label="Modern architectural interior with luxury design"
      >
        <div className="absolute inset-0 bg-zinc-950/70"></div>
      </div>

      <div className="relative z-10 max-w-7xl mx-auto px-6 text-center mt-20">
        <span className="text-amber-500 tracking-[0.3em] text-sm uppercase mb-6 block font-medium">
          Visionary Architecture & Design
        </span>
        <h1 className="text-5xl md:text-7xl lg:text-8xl font-serif text-white mb-8 leading-tight drop-shadow-lg">
          Designing Spaces That <br />
          <span className="italic text-gray-300">Define Your Lifestyle.</span>
        </h1>
        <p className="text-gray-300 max-w-2xl mx-auto mb-12 text-lg font-light leading-relaxed">
          Bespoke architecture, visionary interiors, and seamless turnkey execution for premium residential and commercial environments.
        </p>
        
        <div className="flex flex-col sm:flex-row items-center justify-center gap-6">
          <a href="#contact" className="w-full sm:w-auto px-8 py-4 bg-amber-600 hover:bg-amber-700 text-white tracking-widest text-sm uppercase transition-all duration-300 flex items-center justify-center gap-2">
            Book Free Consultation <ChevronRight size={18} aria-hidden="true" />
          </a>
          <a href="#portfolio" className="w-full sm:w-auto px-8 py-4 border border-white/30 hover:border-white text-white tracking-widest text-sm uppercase transition-all duration-300 flex items-center justify-center gap-2 group">
            <Play size={18} className="group-hover:text-amber-500 transition-colors" aria-hidden="true" /> View Portfolio
          </a>
        </div>
      </div>
    </section>
  );
};

const About = () => {
  return (
    <section id="about" className="py-24 bg-white">
      <div className="max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-16 items-center">
        <div className="relative h-[600px] group overflow-hidden">
          <img 
            src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" 
            alt="Modern interior design showcase with minimalist luxury aesthetic" 
            className="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
            loading="lazy"
          />
          <div className="absolute -bottom-8 -right-8 w-64 h-64 bg-zinc-950 hidden md:flex items-center justify-center p-8 z-10 shadow-2xl">
            <p className="text-white font-serif text-xl leading-relaxed italic">"Architecture is a visual art, and the buildings speak for themselves."</p>
          </div>
        </div>
        
        <div>
          <span className="text-amber-600 tracking-[0.2em] text-sm uppercase mb-4 block font-semibold">The Studio</span>
          <h2 className="text-4xl md:text-5xl font-serif text-zinc-950 mb-8 leading-tight">Where Vision Meets Architecture.</h2>
          <p className="text-zinc-600 leading-relaxed mb-6 font-light text-lg">
            We believe that exceptional design is not just about aesthetics; it is about how a space makes you feel and function. Born from a passion for minimalist elegance and practical luxury, our firm bridges the gap between visionary architecture and flawless turnkey execution.
          </p>
          <p className="text-zinc-600 leading-relaxed mb-10 font-light text-lg">
            From the first sketch to the final styling, we handle every detail so you can simply step into your dream space.
          </p>
          <button className="text-zinc-950 border-b-2 border-amber-500 pb-1 uppercase tracking-widest text-sm hover:text-amber-600 transition-colors flex items-center gap-2 font-semibold">
            Meet Our Team <ArrowRight size={16} aria-hidden="true" />
          </button>
        </div>
      </div>
    </section>
  );
};

const Services = () => {
  const services = [
    { icon: <Home size={32} />, title: "Architectural Design", desc: "Masterful structural planning combining aesthetic brilliance with environmental harmony." },
    { icon: <Layout size={32} />, title: "Interior Design", desc: "Curated, luxurious interior spaces tailored to your personal lifestyle or brand identity." },
    { icon: <Hammer size={32} />, title: "Turnkey Execution", desc: "A stress-free, concept-to-key experience managed entirely by our expert in-house team." },
    { icon: <Building2 size={32} />, title: "Commercial Spaces", desc: "High-performing workspaces and retail environments designed to elevate your brand." }
  ];

  return (
    <section id="services" className="py-24 bg-zinc-950 text-white">
      <div className="max-w-7xl mx-auto px-6">
        <div className="mb-16 md:flex justify-between items-end">
          <div>
            <span className="text-amber-500 tracking-[0.2em] text-sm uppercase mb-4 block font-semibold">Our Expertise</span>
            <h2 className="text-4xl md:text-5xl font-serif leading-tight">End-to-End Design <br/> Solutions.</h2>
          </div>
          <button className="hidden md:flex text-white border-b border-amber-500 pb-1 uppercase tracking-widest text-sm hover:text-amber-500 transition-colors items-center gap-2">
            View All Services <ArrowRight size={16} aria-hidden="true" />
          </button>
        </div>

        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8 border-t border-white/10 pt-12">
          {services.map((srv, idx) => (
            <div key={idx} className="group p-8 border border-white/5 bg-white/5 hover:bg-white/10 hover:border-amber-500/50 transition-all duration-500 cursor-pointer">
              <div className="text-amber-500 mb-8 group-hover:scale-110 transition-transform duration-500" aria-hidden="true">{srv.icon}</div>
              <h3 className="text-2xl font-serif mb-4">{srv.title}</h3>
              <p className="text-zinc-400 font-light leading-relaxed text-sm">{srv.desc}</p>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const Portfolio = () => {
  const projects = [
    { title: "The Horizon Villa", category: "Luxury Residential", img: "https://images.unsplash.com/photo-1613490908592-fd5e23f53199?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" },
    { title: "Zenith Corporate HQ", category: "Commercial", img: "https://images.unsplash.com/photo-1497366216548-37526070297c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" },
    { title: "Lumina Penthouse", category: "Interior Styling", img: "https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" }
  ];

  return (
    <section id="portfolio" className="py-24 bg-zinc-100">
      <div className="max-w-7xl mx-auto px-6">
        <div className="text-center mb-16">
          <span className="text-amber-600 tracking-[0.2em] text-sm uppercase mb-4 block font-semibold">Featured Work</span>
          <h2 className="text-4xl md:text-5xl font-serif text-zinc-950">Masterpieces in Reality.</h2>
        </div>

        <div className="grid md:grid-cols-3 gap-6">
          {projects.map((project, idx) => (
            <div key={idx} className="group relative h-[500px] overflow-hidden bg-zinc-900 cursor-pointer">
              <img 
                src={project.img} 
                alt={project.title} 
                className="absolute inset-0 w-full h-full object-cover opacity-80 group-hover:opacity-40 group-hover:scale-110 transition-all duration-700"
                loading="lazy"
              />
              <div className="absolute inset-0 p-8 flex flex-col justify-end opacity-0 group-hover:opacity-100 transition-opacity duration-500 bg-gradient-to-t from-black/90 to-transparent">
                <span className="text-amber-500 text-xs tracking-widest uppercase mb-2 block">{project.category}</span>
                <h3 className="text-2xl font-serif text-white mb-4">{project.title}</h3>
                <button className="text-white border-b border-white pb-1 text-sm uppercase tracking-widest w-max flex items-center gap-2 hover:text-amber-500 hover:border-amber-500 transition-colors">
                  View Case Study <ArrowRight size={14} aria-hidden="true" />
                </button>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const Testimonials = () => {
  const reviews = [
    { name: "Sarah & James T.", title: "Luxury Villa Owners", text: "They didn't just design our house; they designed a home that perfectly fits our lifestyle. The turnkey process was seamless, transparent, and completely stress-free." },
    { name: "Marcus L.", title: "Tech CEO", text: "Our new office space has completely transformed our company culture. The attention to detail, spatial planning, and modern aesthetic is simply world-class." }
  ];

  return (
    <section id="testimonials" className="py-24 bg-white">
      <div className="max-w-7xl mx-auto px-6">
        <div className="mb-16 text-center">
          <span className="text-amber-600 tracking-[0.2em] text-sm uppercase mb-4 block font-semibold">Client Stories</span>
          <h2 className="text-4xl md:text-5xl font-serif text-zinc-950">The Foundation of Our Trust.</h2>
        </div>

        <div className="grid md:grid-cols-2 gap-10">
          {reviews.map((review, idx) => (
            <div key={idx} className="p-10 bg-zinc-50 border border-zinc-100 shadow-sm hover:shadow-xl transition-shadow duration-300">
              <div className="flex text-amber-500 mb-6" aria-label="5 star rating">
                {[...Array(5)].map((_, i) => <Star key={i} size={18} fill="currentColor" aria-hidden="true" />)}
              </div>
              <p className="text-zinc-600 text-lg font-light leading-relaxed mb-8 italic">"{review.text}"</p>
              <div>
                <h4 className="font-serif text-zinc-950 text-xl">{review.name}</h4>
                <span className="text-xs tracking-widest uppercase text-zinc-400">{review.title}</span>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const ContactCTA = () => {
  const [formData, setFormData] = useState({
    firstName: '',
    lastName: '',
    email: '',
    projectDetails: ''
  });
  const [submitted, setSubmitted] = useState(false);
  const [errors, setErrors] = useState({});

  const validateForm = () => {
    const newErrors = {};
    if (!formData.firstName.trim()) newErrors.firstName = 'First name is required';
    if (!formData.lastName.trim()) newErrors.lastName = 'Last name is required';
    if (!formData.email.trim()) newErrors.email = 'Email is required';
    else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(formData.email)) newErrors.email = 'Invalid email format';
    if (!formData.projectDetails.trim()) newErrors.projectDetails = 'Project details are required';
    return newErrors;
  };

  const handleChange = (e) => {
    const { name, value } = e.target;
    setFormData(prev => ({ ...prev, [name]: value }));
    if (errors[name]) {
      setErrors(prev => ({ ...prev, [name]: '' }));
    }
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const newErrors = validateForm();
    
    if (Object.keys(newErrors).length === 0) {
      console.log('Form submitted:', formData);
      setSubmitted(true);
      setFormData({ firstName: '', lastName: '', email: '', projectDetails: '' });
      setTimeout(() => setSubmitted(false), 5000);
    } else {
      setErrors(newErrors);
    }
  };

  return (
    <section id="contact" className="py-24 bg-zinc-100">
      <div className="max-w-7xl mx-auto px-6">
        <div className="bg-white shadow-2xl flex flex-col md:flex-row">
          <div className="md:w-1/2 p-12 lg:p-20 bg-zinc-950 text-white flex flex-col justify-center relative overflow-hidden">
            <div className="relative z-10">
              <h2 className="text-4xl lg:text-5xl font-serif mb-6 leading-tight">Let's Build Your <br/>Dream Space
