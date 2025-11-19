# Medi-Care-
This is a Doctor Appointment Booking App


import React from 'react';
import { Link } from 'react-router-dom';
import { createPageUrl } from '../utils';
import { Calendar, Clock, Shield, Heart, Star, ArrowRight } from 'lucide-react';
import { Button } from '@/components/ui/button';
import { Card, CardContent } from '@/components/ui/card';

export default function Home() {
  const features = [
    {
      icon: Calendar,
      title: 'Easy Booking',
      description: 'Schedule appointments in just a few clicks',
      color: 'from-blue-500 to-blue-600'
    },
    {
      icon: Clock,
      title: 'Flexible Hours',
      description: 'Multiple time slots to fit your schedule',
      color: 'from-green-500 to-green-600'
    },
    {
      icon: Shield,
      title: 'Secure & Private',
      description: 'Your health information is protected',
      color: 'from-purple-500 to-purple-600'
    },
    {
      icon: Heart,
      title: 'Expert Care',
      description: 'Board-certified doctors across specialties',
      color: 'from-pink-500 to-pink-600'
    }
  ];

  const specialties = [
    { name: 'Cardiology', icon: '❤️', count: '5 Doctors' },
    { name: 'Pediatrics', icon: '👶', count: '8 Doctors' },
    { name: 'Dermatology', icon: '✨', count: '4 Doctors' },
    { name: 'Orthopedics', icon: '🦴', count: '6 Doctors' },
    { name: 'Neurology', icon: '🧠', count: '3 Doctors' },
    { name: 'General Medicine', icon: '🩺', count: '10 Doctors' }
  ];

  return (
    <div className="w-full">
      {/* Hero Section */}
      <section className="relative overflow-hidden bg-gradient-to-br from-blue-600 via-blue-500 to-green-500 text-white">
        <div className="absolute inset-0 bg-white/5 backdrop-blur-3xl"></div>
        <div className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 md:py-32">
          <div className="grid md:grid-cols-2 gap-12 items-center">
            <div className="space-y-8">
              <div className="inline-flex items-center space-x-2 bg-white/20 backdrop-blur-sm px-4 py-2 rounded-full">
                <Star className="w-4 h-4 text-yellow-300 fill-yellow-300" />
                <span className="text-sm font-medium">Trusted by 50,000+ Patients</span>
              </div>
              
              <h1 className="text-5xl md:text-6xl font-bold leading-tight">
                Book Your Next Doctor Appointment
                <span className="block text-green-200">Online</span>
              </h1>
              
              <p className="text-xl text-blue-100 leading-relaxed">
                Connect with top-rated healthcare professionals. Easy scheduling, secure platform, and quality care—all in one place.
              </p>
              
              <div className="flex flex-col sm:flex-row gap-4">
                <Link to={createPageUrl('BookAppointment')}>
                  <Button size="lg" className="bg-white text-blue-600 hover:bg-blue-50 shadow-xl hover:shadow-2xl transition-all duration-300 text-lg px-8 py-6 group">
                    Book Appointment Now
                    <ArrowRight className="w-5 h-5 ml-2 group-hover:translate-x-1 transition-transform" />
                  </Button>
                </Link>
                <Link to={createPageUrl('Doctors')}>
                  <Button size="lg" variant="outline" className="bg-transparent border-2 border-white text-white hover:bg-white hover:text-blue-600 text-lg px-8 py-6">
                    Find a Doctor
                  </Button>
                </Link>
              </div>
            </div>
            
            <div className="hidden md:block">
              <div className="relative">
                <div className="absolute inset-0 bg-gradient-to-r from-blue-400 to-green-400 rounded-3xl blur-3xl opacity-50"></div>
                <img 
                  src="https://images.unsplash.com/photo-1631217868264-e5b90bb7e133?w=600&h=600&fit=crop" 
                  alt="Healthcare Professional" 
                  className="relative rounded-3xl shadow-2xl object-cover w-full h-[500px]"
                />
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-4xl font-bold text-gray-900 mb-4">
              Why Choose MediCare?
            </h2>
            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
              Experience healthcare that puts you first
            </p>
          </div>
          
          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
            {features.map((feature, index) => {
              const Icon = feature.icon;
              return (
                <Card key={index} className="border-0 shadow-lg hover:shadow-xl transition-all duration-300 hover:-translate-y-1">
                  <CardContent className="p-6 text-center">
                    <div className={`w-16 h-16 mx-auto mb-4 bg-gradient-to-br ${feature.color} rounded-2xl flex items-center justify-center shadow-lg`}>
                      <Icon className="w-8 h-8 text-white" />
                    </div>
                    <h3 className="text-xl font-bold text-gray-900 mb-2">
                      {feature.title}
                    </h3>
                    <p className="text-gray-600">
                      {feature.description}
                    </p>
                  </CardContent>
                </Card>
              );
            })}
          </div>
        </div>
      </section>

      {/* Specialties Section */}
      <section className="py-20 bg-gradient-to-br from-blue-50 to-green-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-4xl font-bold text-gray-900 mb-4">
              Featured Specialties
            </h2>
            <p className="text-xl text-gray-600">
              Expert care across all medical fields
            </p>
          </div>
          
          <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-6">
            {specialties.map((specialty, index) => (
              <Card key={index} className="hover:shadow-xl transition-all duration-300 hover:-translate-y-1 cursor-pointer border-0 bg-white">
                <CardContent className="p-6 text-center">
                  <div className="text-4xl mb-3">{specialty.icon}</div>
                  <h3 className="font-semibold text-gray-900 mb-1">
                    {specialty.name}
                  </h3>
                  <p className="text-sm text-gray-500">{specialty.count}</p>
                </CardContent>
              </Card>
            ))}
          </div>
          
          <div className="text-center mt-12">
            <Link to={createPageUrl('Specialties')}>
              <Button size="lg" className="bg-gradient-to-r from-blue-600 to-green-600 hover:from-blue-700 hover:to-green-700 text-white px-8 py-6">
                View All Specialties
                <ArrowRight className="w-5 h-5 ml-2" />
              </Button>
            </Link>
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="py-20 bg-gradient-to-r from-blue-600 to-green-600 text-white">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <h2 className="text-4xl md:text-5xl font-bold mb-6">
            Ready to Take Control of Your Health?
          </h2>
          <p className="text-xl text-blue-100 mb-8">
            Join thousands of satisfied patients who trust us with their healthcare needs
          </p>
          <Link to={createPageUrl('BookAppointment')}>
            <Button size="lg" className="bg-white text-blue-600 hover:bg-blue-50 shadow-xl text-lg px-10 py-6">
              Book Your Appointment Today
              <ArrowRight className="w-5 h-5 ml-2" />
            </Button>
          </Link>
        </div>
      </section>
    </div>
  );
}
