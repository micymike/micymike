import React, { useState } from 'react';
import { Github, Instagram, Mail, ExternalLink, Code, Book, Zap } from 'lucide-react';
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from "@/components/ui/card"
import { Badge } from "@/components/ui/badge"
import { Button } from "@/components/ui/button"
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs"

const skills = [
  { name: 'AWS', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg' },
  { name: 'CSS3', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg' },
  { name: 'Docker', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg' },
  { name: 'Express', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg' },
  { name: 'Flutter', icon: 'https://www.vectorlogo.zone/logos/flutterio/flutterio-icon.svg' },
  { name: 'Git', icon: 'https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg' },
  { name: 'JavaScript', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg' },
  { name: 'MongoDB', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg' },
  { name: 'NestJS', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/nestjs/nestjs-plain.svg' },
  { name: 'Node.js', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg' },
  { name: 'OpenCV', icon: 'https://www.vectorlogo.zone/logos/opencv/opencv-icon.svg' },
  { name: 'PostgreSQL', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg' },
  { name: 'Postman', icon: 'https://www.vectorlogo.zone/logos/getpostman/getpostman-icon.svg' },
  { name: 'Python', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg' },
  { name: 'PyTorch', icon: 'https://www.vectorlogo.zone/logos/pytorch/pytorch-icon.svg' },
  { name: 'React', icon: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg' },
  { name: 'SQLite', icon: 'https://www.vectorlogo.zone/logos/sqlite/sqlite-icon.svg' },
  { name: 'Tailwind', icon: 'https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg' },
  { name: 'Unity', icon: 'https://www.vectorlogo.zone/logos/unity3d/unity3d-icon.svg' },
  { name: 'Zapier', icon: 'https://www.vectorlogo.zone/logos/zapier/zapier-icon.svg' },
];

const DeveloperProfile = () => {
  const [activeTab, setActiveTab] = useState('about');

  return (
    <div className="container mx-auto p-4 max-w-4xl">
      <Card className="w-full">
        <CardHeader>
          <div className="flex items-center justify-between">
            <div>
              <CardTitle className="text-3xl font-bold">Michael Moses</CardTitle>
              <CardDescription className="text-xl">
                Generative AI Specialist | Fullstack Web Dev | ML Enthusiast
              </CardDescription>
            </div>
            <img 
              src="/api/placeholder/150/150" 
              alt="Michael Moses" 
              className="rounded-full w-24 h-24 object-cover"
            />
          </div>
        </CardHeader>
        <CardContent>
          <Tabs value={activeTab} onValueChange={setActiveTab} className="w-full">
            <TabsList className="grid w-full grid-cols-3">
              <TabsTrigger value="about">About</TabsTrigger>
              <TabsTrigger value="skills">Skills</TabsTrigger>
              <TabsTrigger value="projects">Projects</TabsTrigger>
            </TabsList>
            <TabsContent value="about">
              <div className="space-y-4">
                <p>🔭 I'm currently working on ..</p>
                <p>🌱 I'm currently learning flutter, nestjs</p>
                <p>👯 I'm looking to collaborate on AI projects</p>
                <p>⚡ Fun fact: I like dancing and learning new things each day.</p>
              </div>
            </TabsContent>
            <TabsContent value="skills">
              <div className="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
                {skills.map((skill) => (
                  <div key={skill.name} className="flex flex-col items-center">
                    <img src={skill.icon} alt={skill.name} className="w-12 h-12" />
                    <span className="mt-2 text-sm">{skill.name}</span>
                  </div>
                ))}
              </div>
            </TabsContent>
            <TabsContent value="projects">
              <div className="space-y-4">
                <p>All of my projects are available at my portfolio website.</p>
                <Button variant="outline">
                  <ExternalLink className="mr-2 h-4 w-4" />
                  Visit Portfolio
                </Button>
              </div>
            </TabsContent>
          </Tabs>
        </CardContent>
        <CardFooter className="flex justify-between">
          <div className="flex space-x-2">
            <Badge variant="outline" className="flex items-center">
              <Code className="mr-1 h-3 w-3" /> Python
            </Badge>
            <Badge variant="outline" className="flex items-center">
              <Code className="mr-1 h-3 w-3" /> React
            </Badge>
            <Badge variant="outline" className="flex items-center">
              <Code className="mr-1 h-3 w-3" /> JavaScript
            </Badge>
          </div>
          <div className="flex space-x-2">
            <Button variant="ghost" size="icon">
              <Instagram className="h-4 w-4" />
            </Button>
            <Button variant="ghost" size="icon">
              <Github className="h-4 w-4" />
            </Button>
            <Button variant="ghost" size="icon">
              <Mail className="h-4 w-4" />
            </Button>
          </div>
        </CardFooter>
      </Card>
    </div>
  );
};

export default DeveloperProfile;
