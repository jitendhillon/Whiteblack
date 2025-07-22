port { Phone, Mail, MapPin, ExternalLink } from "lucide-react";

export const Footer = () => {
  const currentYear = new Date().getFullYear();

  const quickLinks = [
    { name: "Home", href: "#hero" },
    { name: "About", href: "#about" },
    { name: "Services", href: "#services" },
    { name: "Testimonials", href: "#testimonials" },
    { name: "Contact", href: "#contact" }
  ];

  const services = [
    "Vehicle Challan Resolution",
    "Document Notarisation", 
    "Legal Document Preparation",
    "Court Filing Services",
    "Legal Consultation"
  ];

  const scrollToSection = (sectionId: string) => {
    const element = document.querySelector(sectionId);
    element?.scrollIntoView({ behavior: 'smooth' });
  };

  return (
    <footer className="bg-gradient-primary text-primary-foreground">
      <div className="container mx-auto px-4 py-12">
        <div className="grid md:grid-cols-4 gap-8">
          {/* Company Info */}
          <div className="md:col-span-1">
            <div className="flex items-center space-x-3 mb-6">
              <img 
                src="/lovable-uploads/2d074c9e-ddc3-43a8-ba28-f17f7a759768.png" 
                alt="WhiteBlack Associates Logo"
                className="h-8 w-auto object-contain brightness-0 invert"
              />
              <div>
                <h3 className="text-xl font-bold">WhiteBlack Associates</h3>
                <p className="text-sm text-primary-foreground/80">Legal Excellence</p>
              </div>
            </div>
            <p className="text-primary-foreground/80 mb-6 leading-relaxed">
              Futuristic legal solutions rooted in justice. Professional legal services with modern efficiency and traditional expertise.
            </p>
            <div className="space-y-2 text-sm">
              <div className="flex items-center space-x-2">
                <MapPin className="h-4 w-4" />
                <span>F-60, Kamla Nagar, Delhi</span>
              </div>
              <div className="flex items-center space-x-2">
                <Phone className="h-4 w-4" />
                <span>+91-9416888809</span>
              </div>
            </div>
          </div>

          {/* Quick Links */}
          <div>
            <h4 className="text-lg font-semibold mb-6">Quick Links</h4>
            <ul className="space-y-3">
              {quickLinks.map((link) => (
                <li key={link.name}>
                  <button
                    onClick={() => scrollToSection(link.href)}
                    className="text-primary-foreground/80 hover:text-primary-foreground transition-colors text-sm"
                  >
                    {link.name}
                  </button>
                </li>
              ))}
            </ul>
          </div>

          {/* Services */}
          <div>
            <h4 className="text-lg font-semibold mb-6">Our Services</h4>
            <ul className="space-y-3">
              {services.map((service) => (
                <li key={service}>
                  <span className="text-primary-foreground/80 text-sm">
                    {service}
                  </span>
                </li>
              ))}
            </ul>
          </div>

          {/* Contact & Legal */}
          <div>
            <h4 className="text-lg font-semibold mb-6">Contact & Legal</h4>
            <div className="space-y-4">
              <div>
                <p className="text-sm font-medium mb-2">Office Hours</p>
                <p className="text-primary-foreground/80 text-sm">
                  Monday–Saturday<br />
                  9:30 AM – 7:00 PM
                </p>
              </div>
              <div>
                <p className="text-sm font-medium mb-2">Email</p>
                <a 
                  href="mailto:contact@whiteblacklegal.com"
                  className="text-primary-foreground/80 hover:text-primary-foreground transition-colors text-sm flex items-center space-x-1"
                >
                  <Mail className="h-4 w-4" />
                  <span>contact@whiteblacklegal.com</span>
                </a>
              </div>
            </div>
          </div>
        </div>

        {/* Bottom Bar */}
        <div className="border-t border-primary-foreground/20 mt-12 pt-8">
          <div className="flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
            <div className="text-sm text-primary-foreground/80">
              © {currentYear} WhiteBlack Associates | Advocate Jiten Dhillion | All Rights Reserved
            </div>
            <div className="flex items-center space-x-6 text-sm">
              <button className="text-primary-foreground/80 hover:text-primary-foreground transition-colors">
                Terms & Conditions
              </button>
              <button className="text-primary-foreground/80 hover:text-primary-foreground transition-colors">
                Privacy Policy
              </button>
              <a 
                href="#"
                className="text-primary-foreground/80 hover:text-primary-foreground transition-colors flex items-center space-x-1"
              >
                <span>LinkedIn</span>
                <ExternalLink className="h-3 w-3" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  );
