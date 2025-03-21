# evnt
import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Search } from "lucide-react";

const events = [
  { title: "Abilene Farmers Market", date: "March 25, 2025", location: "Downtown Abilene" },
  { title: "Live Music at The Mill", date: "March 28, 2025", location: "The Mill Winery" },
  { title: "West Texas Rodeo", date: "April 5, 2025", location: "Expo Center" },
];

const news = [
  { title: "New Restaurant Opens Downtown", date: "March 20, 2025", summary: "A brand new dining experience has launched in downtown Abilene..." },
  { title: "City Council Approves New Park", date: "March 18, 2025", summary: "The city council has voted to develop a new public park..." },
  { title: "Abilene Zoo Welcomes New Animals", date: "March 15, 2025", summary: "The Abilene Zoo introduces a group of exotic animals to its collection..." },
];

const sponsors = [
  { name: "Abilene Coffee Roasters", description: "Locally sourced coffee with rich flavors.", website: "#" },
  { name: "Frontier Outfitters", description: "Your go-to store for outdoor gear and apparel.", website: "#" },
  { name: "Texas BBQ Haven", description: "Authentic Texas-style BBQ, slow-cooked to perfection.", website: "#" },
];

export default function AbileneEventsHub() {
  return (
    <div className="min-h-screen bg-gray-100 p-6">
      <header className="text-center text-4xl font-bold text-blue-600 mb-6">
        Abilene Local Events & News Hub
      </header>
      <div className="flex justify-center mb-6">
        <Input className="w-1/2" placeholder="Search events..." />
        <Button className="ml-2">
          <Search className="w-5 h-5" />
        </Button>
      </div>
      <section className="mb-12">
        <h2 className="text-2xl font-semibold text-gray-800 mb-4">Upcoming Events</h2>
        <div className="grid md:grid-cols-3 gap-6">
          {events.map((event, index) => (
            <Card key={index} className="p-4 shadow-lg">
              <CardContent>
                <h3 className="text-xl font-semibold">{event.title}</h3>
                <p className="text-gray-600">{event.date}</p>
                <p className="text-gray-500">{event.location}</p>
                <Button className="mt-4 w-full">Get Tickets</Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>
      <section className="mb-12">
        <h2 className="text-2xl font-semibold text-gray-800 mb-4">Local News</h2>
        <div className="grid md:grid-cols-3 gap-6">
          {news.map((article, index) => (
            <Card key={index} className="p-4 shadow-lg">
              <CardContent>
                <h3 className="text-xl font-semibold">{article.title}</h3>
                <p className="text-gray-600">{article.date}</p>
                <p className="text-gray-500">{article.summary}</p>
                <Button className="mt-4 w-full">Read More</Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>
      <section className="mb-12">
        <h2 className="text-2xl font-semibold text-gray-800 mb-4">Local Spotlights</h2>
        <div className="grid md:grid-cols-3 gap-6">
          {sponsors.map((sponsor, index) => (
            <Card key={index} className="p-4 shadow-lg">
              <CardContent>
                <h3 className="text-xl font-semibold">{sponsor.name}</h3>
                <p className="text-gray-600">{sponsor.description}</p>
                <Button className="mt-4 w-full" asChild>
                  <a href={sponsor.website} target="_blank" rel="noopener noreferrer">Visit Website</a>
                </Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>
    </div>
  );
}
